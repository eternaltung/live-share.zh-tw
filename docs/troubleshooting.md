---
title: 疑難排解-Visual Studio 即時共用 |Microsoft Docs
description: Visual Studio Live Share 疑難排解祕訣和訣竅。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8d20ec73d9cadfefced65c04b1ef18f6e844167d
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255513"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>疑難排解 Visual Studio 即時共用

本文章涵蓋疑難排解的秘訣、 因應措施，以及常見的問題和問題的解答。 您也可以看看[常見問題集](faq.md)。

## <a name="installation--tool-requirements"></a>安裝 / 工具需求

以下疑難排解的秘訣與安裝 Visual Studio Live Share。

| 工具 | 問題 | 解決方式 / 因應措施 |
|------|---------|------------|
| VS | 擴充功能安裝程式<strong>找不到 Visual Studio 版本</strong>時嘗試安裝 Visual Studio Live Share 延伸模組使用。 | 需要 visual Studio Live Share **Visual Studio 2017 15.6 版**以上的主機和來賓。 安裝最新的穩定[Visual Studio 2017 的更新](https://visualstudio.com/vs/)，然後重試。|
| VS Code | 嘗試在 macOS 上使用 Visual Studio Live Share 使用 VS Code 時，就會出現錯誤<strong>El Capitan 或以下版本</strong>。 | Visual Studio Live Share 的作業系統支援是取決於.NET Core 的目前[只支援 macOS Sierra 與更新版本。]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | 「**無法安裝相依性**」 就會出現錯誤時延伸模組**完成安裝**初次啟動，或取得有關錯誤**遺漏或已有檔案**. | 請確認您位於**良好的網路連線**。 如果您是，您可能執行到**proxy 或防火牆**問題。 請參閱[連線疑難排解](#connectivity)。 <br /><br />|
| VS Code | 從 marketplace 安裝 Visual Studio Live Share 延伸模組<strong>將它安裝在 VS Code 的穩定/測試人員版本</strong>而不是我想要的版本。 | 啟動 VS Code 穩定或根據您的喜好設定的測試人員，按一下 [擴充功能] 索引標籤上，搜尋"Visual Studio Live Share"並從該處安裝。 |
| VS 程式碼 (**Linux**) | Live Share 延伸模組不會啟動並**不顯示任何狀態列項目**上安裝擴充功能之後**Linux**。 | Visual Studio Live Share 取決於.NET Core 2.0 具有一些 Linux 必要條件可能不符合特定的 Linux 散發套件上的預設值。 請參閱[如需詳細資訊，這裡](reference/linux.md#install-linux-prerequisites)上應該要安裝的項目。 |

## <a name="sign-in"></a>登入

以下疑難排解登入問題的秘訣。

| 工具 | 問題 | 解決方式 / 因應措施 |
|------|---------|------------|
| VS | 您需要登入 Visual Studio Live Share 與<strong>不同的身分識別</strong>讓您用來登入 Visual Studio。 | 移至工具 > 選項 > Live Share > 若要選取其他帳戶的使用者帳戶。 |
| VS Code | 瀏覽器視窗中顯示登入期間和處理程序時<strong>就會在網頁上成功</strong>，[狀態] 列<strong>還是說 「 登入 」</strong>之後關閉瀏覽器。 | 登入之後，按一下 "時發生問題嗎？ 」 並遵循指示輸入工具暫時的使用者程式碼。<br /><br />我們也很樂意以查看線索，因此請[記錄 bug](https://aka.ms/vsls-problem)。 |
| 全部 | 您會收到<strong>逾時或連線錯誤</strong>。 | 請參閱[連線疑難排解](#connectivity)。 |
| 全部 | 當使用 Microsoft 登入支援**工作或學校電子郵件地址**您會看到訊息指出， **「 需要系統管理員核准 」**。 | 您的 Azure AD 租用戶是設定為需要存取目錄的內容的新應用程式的 「 系統管理員同意 」。 請參閱[此處](reference/security.md)如需詳細資訊。 |
| VS Code (**macOS**) | 登入您時看到錯誤指出**SecKeychainAddGenericPassword() 失敗**。 | 這幾乎都是因為 macOS 的常見問題，密碼變更不會反映在 登入鑰匙圈。 請嘗試進入 「 鑰匙圈存取 」、 鎖定登入金鑰鏈，然後再解除鎖定它。 這可能不足以解決此問題，但如果您無法使用目前的密碼、 解除鎖定嘗試您的上一個。 如果可行，請將登入金鑰鏈密碼變更為您目前的密碼。 請參閱[此處](https://support.apple.com/en-us/HT201609)如需詳細資訊。 |
| VS 程式碼 (**Linux**) | 透過瀏覽器登入之後，使用者程式碼中輸入時看到錯誤指出**secret_password_store_sync() 失敗，錯誤碼為 XX**。 | 這通常是由於`gnome-keyring`及/或`libsecret-1-0` /  `libsecret`未安裝。 您可以驗證 gnome keyring 已正確設定安裝`seahorse`，然後在您的桌面環境中使用 「 密碼和金鑰 」 應用程式。 深入了解[以下 Linux 必要條件](reference/linux.md#install-linux-prerequisites)。 |
| VS 程式碼 (**Linux**) | 就<strong>提示您輸入使用者程式碼</strong>Live Share v0.3.295 或以下，但瀏覽器不會顯示可讓您取得訂用帳戶。 | 我們正努力排除在 Linux 上的使用者程式碼需求。 時間，在瀏覽器視窗應該會出現供您用來登入。 如果沒有，則瀏覽器視窗可能會隱藏在 VS Code。 如果這不是，請參閱下一步 的提示。  |
| VS Code | 按一下 登入 之後 (或使用 「 即時共用：登入 命令），<strong>任何瀏覽器視窗隨即出現，可讓您輸入認證</strong>。 | 1.[在此登入](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2.登入之後，按一下 "時發生問題嗎？ 」<br /> 3.遵循指示以輸入工具暫時的使用者程式碼。 |
| 全部 | 您想要<strong>聯結</strong>共同作業工作階段</strong>但<strong>還沒 / 不要接收電子郵件更新</strong>。 | 登入 VS/VS 程式碼中的 Live Share 延伸模組並未<strong>不</strong>您選擇加入接收電子郵件更新。<br /><br />即時共用需要主應用程式都會看到這些加入的身分識別，因此基於安全性考量登入的來賓。 [這項功能投贊成票](https://github.com/MicrosoftDocs/live-share/issues/3)如果您想要允許匿名使用者加入的選項 (例如沒有名稱的使用者 / 使用者定義的名稱)。 |

## <a name="share-and-join"></a>共用和聯結

以下疑難排解登入問題的秘訣。

| 工具 | 問題 | 解決方式 / 因應措施 |
|------|----------------|------------|
| 全部 | <strong>共用/聯結：</strong>您會收到逾時或無法連線的相關錯誤。 | 請參閱[連線疑難排解](#connectivity)。 |
| VS Code | <strong>聯結：</strong>你<strong>未提示 / 能夠啟動 VS Code</strong>瀏覽器中開啟 [加入] 頁面之後。 |  祕訣： <ul><li>確定您已<i>至少一次啟動 VS Code 並等候安裝完成狀態 列中。</i></li><li>如果不行，請嘗試在執行 「 即時共用：啟動器 Setup"命令。</li><li>**Linux 使用者**:出現提示時輸入您的系統管理員 (sudo) 密碼，執行上述命令時，請這麼做。</li><li>最後，請參閱 <<c0> [ 手動聯結](reference/manual-join.md)因應措施。</li></ul> 如果您遇到這個問題，我們很樂意以查看線索，因此請[記錄 bug](https://aka.ms/vsls-new-issue)。 |
| VS | <strong>聯結：</strong>你<strong>未提示 / 能夠啟動 VS</strong>瀏覽器中開啟 [加入] 頁面之後。 |  請參閱[手動聯結](reference/manual-join.md)。<br /><br /> 我們也希望看到您的記錄，因此請[記錄 bug](https://aka.ms/vsls-problem)使用 Visual Studio 的 「 報告問題...」功能。 |
| 全部 | <strong>聯結：</strong>您不希望<strong>加入連結直接貼入 Visual Studio / VS Code</strong>而不是按一下 web 連結。 | 請參閱[手動聯結](reference/manual-join.md)。 |
| 全部 | <strong>聯結：</strong>您會看到訊息指出，「**工作區的擁有者似乎是離線**，"聯結透過瀏覽器時。 | 可能的因應措施：<br /><ul><li>請嘗試[手動聯結](reference/manual-join.md)。 我們已經看到跨區域的問題 (例如東部和西部美國) 因為服務問題，不會影響聯結的聯結。</li><li>即時共用可能無法直接路由至主應用程式在 「 自動 」 連線模式中執行時。 請嘗試[轉送模式](reference/connectivity.md)。</li></ul>請參閱[連線疑難排解](#connectivity)的更多可能性 |
| VS Code | <strong>聯結：</strong>您加入透過瀏覽器<strong>登入前先</strong>，已不提示您登入</strong>，並永遠不會完成聯結。 |  這是[已知的錯誤](https://github.com/MicrosoftDocs/live-share/issues/167)。 按一下登入狀態的工具列項目，登入，然後再加入一次。 |

## <a name="connectivity"></a>連線能力

下列資訊可協助您排解疑難，如果您遇到問題時的相關連線或逾時登入，共用或聯結。

中所述[Live Share 的連線需求](reference/connectivity.md)文章中，不同的連接模式有函式，如此有幾個不同的潛在問題，在不同的需求。

| 工具 | 問題 | 可能的原因 |
|------|------|----------------|
| 全部 | 您使用<strong>proxy</strong>並看到許多連線問題 | Proxy 設定可能很難。  請嘗試設定**HTTP_PROXY**並**HTTPS_PROXY**環境變數**全域**後再重新啟動您的工具。 請參閱[proxy 設定](reference/connectivity.md#proxies)如需詳細資訊。 可能有一些設定，我們尚不支援，因此[讓我們知道](https://github.com/MicrosoftDocs/live-share/issues/86)如果這不適用於您。 |
| VS Code | 安裝延伸模組，並啟動 VS Code，第一次之後得到<strong>錯誤出現在狀態列中的 「 完成安裝 」 時</strong>。 |  您無法存取網際網路或 download.visualstudio.microsoft.com 存取及/或您的個人或公司防火牆會封鎖連接埠 443 上的 download.microsoft.com。 請參閱[此處](https://github.com/MicrosoftDocs/live-share/issues/58)了解為何 Live Share 需要在此時下載某項目。 |
| 全部 | 您是<strong>無法登入 Visual Studio Live Share</strong> | 您無法存取網際網路，或存取 *。 liveshare.vsengsaas.visualstudio.com 連接埠 80/443 防火牆會封鎖您個人或公司。 輸入 https://insiders.liveshare.vsengsaas.visualstudio.com瀏覽器中，並確認您登陸在 Visual Studio Live Share 首頁上。 |
| 全部 | 您處於<strong>auto 模式</strong>（預設值），能夠登入，但請參閱<strong>逾時或連線錯誤</strong>共用，或加入時。 | 請同時直接和轉送來連接失敗模式，或使用 auto 模式的 bug。 如果您之後無法連接[切換為直接或轉送模式](reference/connectivity.md#changing-the-connection-mode)，請[引發錯誤](https://aka.ms/vsls-problem)。 |
| 全部 | 您處於<strong>直接模式</strong>，能夠登入，但請參閱<strong>逾時或連線錯誤</strong>共用，或加入時。 | 在來賓和主機無法直接連線。 請嘗試[自動] 或 [轉送模式](reference/connectivity.md#changing-the-connection-mode)若要查看問題是否就會消失。 您可能需要[手動允許通過個人防火牆的 Live Share](reference/connectivity.md#manually-adding-a-firewall-entry) ，或只使用轉送模式。 |
| 全部 | 您處於<strong>轉送模式</strong>，能夠登入，但收到的通知<strong>逾時或連線錯誤</strong>共用，或加入時。 | 存取 *。 servicebus.windows.net 連接埠 80/443 會封鎖您的個人或公司防火牆封鎖。 請嘗試[直接模式](reference/connectivity.md#changing-the-connection-mode)。 |

請參閱[Live Share 的連線需求](reference/connectivity.md)文章中的，如需有關連線需求。

## <a name="see-also"></a>另請參閱

快速入門

- [共用您的第一個專案](quickstart/share.md)
- [加入您的第一個工作階段](quickstart/join.md)

做法

- [使用 Visual Studio Code 共同作業](use/vscode.md)
- [使用 Visual Studio 共同作業](use/vs.md)

參考資料

- [所有主要 bug、 功能要求和限制](https://aka.ms/vsls-issues)
- [所有的功能要求和限制](https://aka.ms/vsls-feature-requests)
- [Live Share 的連線需求](reference/connectivity.md)
- [Linux 安裝詳細資料](reference/linux.md)
- [語言和平台支援](reference/platform-support.md)
- [延伸模組支援](reference/extensions.md)

仍然有問題嗎？ 您可以[提供意見反應](support.md)。
