---
title: 連線-Visual Studio 即時共用 |Microsoft Docs
description: Visual Studio Live Share 上連線與連接模式資訊。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c685df798fc10b449c3e73db678e3b5d34e73ef0
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640077"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Live Share 的連線需求

本文摘要說明 Visual Studio Live Share、 可用的連線選項，以及已知的因應措施時適用的連線需求。

## <a name="sign-in"></a>登入

您可以登入使用任何的 Live Share [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory)備份的工作或學校帳戶[的 Microsoft 帳戶](https://account.microsoft.com/account)，或[GitHub 設定檔](https://github.com/)。 通常在登入 Url 為這些是在指定的數字的公用面向產品時所使用，但是如果不是，大部分的組織中開啟，請連絡網路系統管理員，開啟`login.microsoftonline.com`及/或`github.com`除了網域[以下列出](#requirements-for-connection-modes)。

> [!NOTE]
> 在內部部署 AD (ADFS) 帳戶和內部部屬 GitHub Enterprise 帳戶目前不支援[(投票👍)](https://github.com/MicrosoftDocs/live-share/issues/341)。

## <a name="connection-modes"></a>連接模式

若要確保最佳效能，預設 Visual Studio Live Share 會自動偵測是否的共同作業工作階段主機和來賓機器可以直接透過網路進行通訊，以及它們之間沒有路由時，只轉送透過雲端。 此混合的 「 自動 」 模式具有彈性，甚至允許透過雲端轉送某些來賓，而其他人連接直接針對相同的工作階段。

透過雲端式機制來確保安全性，但需要 5990 5999 之間的連接埠開啟，讓連線驗證直接的連線。 如此一來，當第一次共用您的桌面防火牆可能會提示您開啟連接埠。 接受 這選擇性的 as 略過只會造成 Live Share 一律使用 在 auto 模式中的轉送。

在 Visual Studio Live Share 的所有連線都都 SSH 或 SSL 加密，並針對提供集中的服務驗證，以確保只有在共同作業工作階段才能存取其內容。 此外，Live Share 雲端轉送不會保存任何透過它路由傳送的流量，而且不會不"窺探 」 以任何方式的流量。

## <a name="changing-the-connection-mode"></a>變更連線模式

如果您想要停用直接或轉送的連線，或只疑難排解連線問題，您可以強制其他的連接模式。

| 模式 | 主應用程式行為 | 客體行為 |
|------|----------------|----------------------|
| 自動 | 安全、 已驗證的直接連線或雲端轉送連線，可接受主機的共同作業工作階段。 | 嘗試將使用直接連接，並會回復為透過雲端進行轉送，如果此作業失敗。 |
| 直接 | 主機的共同作業工作階段只接受已驗證且安全的直接連線。 | 嘗試使用直接連接，如果它無法連線就會停止。 |
| Relay | 主機的共同作業工作階段不允許直接連接。 在主機電腦上不開啟任何連接埠。 | 一律會透過雲端連線。 |

若要變更的模式：

**VS:**

1. 移至工具 > 選項 > 即時共用。
2. 從 「 連接模式 」 的下拉式清單中選取的模式。
3. 重新啟動 VS。

**VS 程式碼：**

1. 編輯 settings.json (檔案 > 喜好設定 > 設定)。
2. 設定`"liveshare.connectionMode"`要`"auto"`， `"direct"`，或`"relay"`視您的喜好設定而定。
3. 重新啟動 VS Code。

## <a name="requirements-for-connection-modes"></a>連接模式的需求

您是在連線模式會指定特定連接埠和 Url 必須可供 Live Share 函式。

| 模式 | 用戶端存取需求 | 疑難排解 |
|------|--------------|-----------------|
| 任何 | 輸出存取 `*.liveshare.vsengsaas.visualstudio.com:443` | 請確定您的公司或個人網路防火牆可讓您連線到此網域。 輸入 https://insiders.liveshare.vsengsaas.visualstudio.com瀏覽器中，並確認您登陸在 Visual Studio Live Share 首頁上。 您可能也會遇到[proxy 問題](#proxies)需要解析。|
| 任何 (VS Code) | 輸出存取 `download.microsoft.com:443` | 請確定您的公司或個人網路防火牆可讓您連線到此網域。 您可能也會遇到[proxy 問題](#proxies)需要解析。 |
| 自動 | 自動切換。 請參閱直接和轉送模式。 | 切換至直接或轉送進行疑難排解的模式。 |
| 直接 | 主機：中範圍 5990 5999 需求以接受輸入的區域網路連接開啟的連接埠。<br /><br />客體作業系統︰網路路由和主應用程式在此相同的連接埠的輸出存取。 | 請確認 「 vsls 代理程式 」 不會封鎖您的桌面防火牆軟體，此連接埠範圍，而且您可以 ping 另一個。 雖然 Windows 和其他桌面軟體應該會提示您第一次啟動代理程式，我們討論過其中的群組原則防止這種情況，而您需要的執行個體[手動新增項目](#manually-adding-a-firewall-entry)。 您可能也會遇到[proxy 問題](#proxies)需要解析。 |
| Relay | 對外存取`*.servicebus.windows.net:443`。 | 請確定您的公司或個人網路防火牆可讓您連線到此網域。 您可能也會遇到[proxy 問題](#proxies)需要解析。|

## <a name="manually-adding-a-firewall-entry"></a>手動新增的防火牆項目

如上面所述，直接模式需要您的個人防火牆允許**vsls 代理程式**接受連線，請在連接埠範圍 5990 5999。 如果您想要使用直接模式，但發現您的防火牆沒有 vsls 代理程式項目，您可以手動新增。 如何這麼做會因防火牆軟體，但您可以找到有關的資訊 **[設定 Windows 防火牆](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**。

如果看不到 vsls 代理程式的項目，您可以在下列位置，找到代理程式可執行檔。

### <a name="vs-code-agent-location"></a>VS 程式碼代理程式位置

Substitute**版本**延伸模組的版本號碼，其中一種下列路徑：

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Visual Studio 代理程式位置

Visual Studio 位置是更動態的但您可以遵循下列步驟來尋找可執行檔：

1. 瀏覽至您的 Visual Studio 安裝位置。 這通常是`C:\Program Files (x86)\Microsoft Visual Studio\EDITION`何處**EDITION**是 Community、 Enterprise 等

2. 執行搜尋，以針對`vsls-agent.exe`在底下**IDE\Extensions**子資料夾。

不幸的是，您可能需要執行此步驟**每次您更新 Visual Studio Live Share。**

## <a name="proxies"></a>Proxy

Visual Studio Live Share 目前有周圍 proxy 使用的一些限制。 自動 proxy 設定應該作用於 Windows、 macOS 或 Linux 使用時 （與特定 proxy 設定，在 Windows 上） 時**HTTP_PROXY**並**HTTPS_PROXY**需要環境變數設定*全域*。

如果您的 proxy 不會自動設定這些，您可以手動設定的變數，以下列形式：

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

如果您有驗證 proxy，您可以加入您的使用者和密碼，如下所示：

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

如果這些設定不為您解決問題[請讓我們知道](https://github.com/MicrosoftDocs/live-share/issues/86)讓我們可以看看改善支援，設定您的 proxy 的詳細資訊。

## <a name="see-also"></a>另請參閱

- [操作說明：使用 Visual Studio Code 共同作業](../use/vscode.md)
- [如何：使用 Visual Studio 共同作業](../use/vs.md)
- [Live Share 的安全性功能](security.md)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
