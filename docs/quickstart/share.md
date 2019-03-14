---
title: 共用的快速入門-Visual Studio Live Share |Microsoft Docs
description: 共用您的第一個專案使用 Visual Studio Live Share 共同作業工作階段縮減逐步解說。
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255498"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>快速入門：共用您的第一個專案

> **注意：Visual Studio Live Share 目前為預覽狀態。使用者體驗和功能不是最終版本。**

歡迎使用 Visual Studio Live Share！ Live Share 可讓您即時與其他人以共同作業方式編輯和偵錯，不論您所使用程式設計語言或建置的應用程式類型為何。 它可讓您立即且安全地共用您目前的專案，然後視需要共用偵錯工作階段、終端機執行個體、localhost Web 應用程式、語音通話等！

準備好開始著手了嗎？  因此快速且自然，就不難這麼做，應該是小組共同作業 ！ 基於這個理由，Visual Studio Live Share 可簡化開始使用，以便您可以無接縫地開始共用您的工作和想法。

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在兩個執行個體中使用相同的身分識別。 趕緊去瞧一瞧！

只要遵循下列步驟以開始共用。

## <a name="1-install-the-extension"></a>1.安裝擴充功能

安裝延伸模組很簡單。 只要遵循下列步驟：

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. 安裝適用於 Windows (7、8.1 或 10)、macOS <b>(Sierra+)</b>、64 位元 Linux <b>的 <a href="https://code.visualstudio.com/">Visual Studio Code</a> (<a href="../use/vscode.md#installation">詳細資料</a>)</b><br />
        2. 從 Marketplace 下載並安裝 Visual Studio Live Share 延伸模組。 <br />
        3. 重新載入並等候相依性下載和安裝 (查看狀態列)。<br />
        4. <strong>Linux</strong>：如果系統提示<a href="../reference/linux.md#install-linux-prerequisites">安裝程式庫</a>，請按一下 [安裝]、輸入密碼，並在完成時重新啟動 VS Code。<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017 15.6 (含) 以上版本</strong><br />
        1. 在 Windows (7、8.1 或 10) 上安裝最新版本的 <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6+)。<br/>
        2. 安裝<a href="../reference/platform-support.md">支援的工作負載</a> (例如 ASP.NET、.NET Core、C++ 及/或 Node.js)。<br />
        3. 從 Marketplace 下載並安裝 Visual Studio Live Share 延伸模組。 <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. 安裝 <a href="https://aka.ms/vs-preview">Visual Studio 2019</a> 的最新預覽版本。<br/>
        2. 安裝<a href="../reference/platform-support.md">支援的工作負載</a> (例如 ASP.NET、.NET Core、C++ 及/或 Node.js)。<br />
        3. Visual Studio Live Share 預設已安裝這些工作負載。 <br />
    </td>
</tr>
</table>

下載並使用 Visual Studio Live Share 即表示您同意[授權條款](https://aka.ms/vsls-license)和[隱私權聲明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)。 如果您遇到問題，請參閱[疑難排解](../troubleshooting.md)。

## <a name="2-sign-in"></a>2.登入

安裝 Live Share 延伸模組、 重新啟動，並等待相依性，以完成安裝 (VS Code) 之後, 您會想要讓其他參與者了解您的身分登入。 只要按一下 「 即時共用 」 狀態列項目 (VS Code) / [登入] 按鈕 (VS) 開始。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

在  **VS Code**，通知會出現要求您登入的啟動時，將會啟動您的瀏覽器。 完成登入您的瀏覽器中的程序，然後只需關閉瀏覽器完成。

![使用網頁瀏覽器登入要求的快顯通知](../media/vscode-sign-in-toast.png)

> **Linux 使用者：** 您可能會提示您輸入使用者程式碼，如果您使用較舊版本的 Live Share (v0.3.295 或以下版本)。 更新延伸模組的最新版本，或按一下 「 需要疑難排解嗎？ 」 連結登入之後，以查看程式碼。 請參閱[如需詳細資訊，這裡](../use/vscode.md#sign-in-using-a-user-code)。

在  **Visual Studio**，Live Share 會自動使用您[個人化帳戶](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)。 如此一來，您可以直接登入可以用正常方式。 不過，如果您想要使用的不同登入與您的 Visual Studio 個人化帳戶時，請移至**工具&gt;選項&gt;Live Share&gt;使用者帳戶**並選取不同的認證。

請參閱[疑難排解](../troubleshooting.md#sign-in)如果仍然發生問題。

## <a name="3-open-a-folder-project-or-solution"></a>3.開啟資料夾、 專案或方案

您可以使用一般工作流程來開啟資料夾、 專案或您想要在 Visual Studio 或 Visual Studio Code 中共用的解決方案。

### <a name="4-optional-update-hidden-or-excluded-files"></a>4.[選擇性] 更新隱藏或排除的檔案

根據預設，Live Share**隱藏**.gitignore 檔案，在您從來賓的共用資料夾中參考的任何檔案/資料夾。 **隱藏**檔案可防止客體的檔案樹狀結構中出現。 **排除**就會套用更嚴格的規則，避免 Live Share 開啟來賓在移至定義，或如果您的檔案在時逐步執行偵錯，或 「 遵循 」 的情況中的檔案。 如果您想要不同的檔案/排除隱藏 **。 vsls.json**檔案可以新增至您的專案，使用這些設定。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)如需詳細資訊。

## <a name="5-start-a-collaboration-session"></a>5.開始共同作業工作階段

接下來，只要在您的工具中按一下"Live Share"並邀請連結會自動複製到剪貼簿。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> 您可能會要求您的桌面防火牆軟體所允許 Live Share 的代理程式在您共用的第一次開啟連接埠。 接受這完全是選擇性的但可讓受保護 「 直接模式 」 來改善效能，因為您正在使用的人員是在相同網路上時。 請參閱[變更連線模式](../reference/connectivity.md#changing-the-connection-mode)如需詳細資訊。

## <a name="6-optional-enable-read-only-mode"></a>6.[選擇性] 啟用唯讀模式

一旦您開始您的共同作業工作階段，您可以設定為唯讀，以防止來賓對共用的程式碼進行編輯的工作階段。

共用之後, 您會收到通知，邀情連結，已複製到剪貼簿。 然後，您可以選取的選項，讓工作階段，唯讀狀態。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

在  **VS Code**，您也可以從 Live Share viewlet 索引標籤來啟動的唯讀工作階段。

![使用網頁瀏覽器登入要求的快顯通知](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7.邀情連結傳送給某人

透過電子郵件、 Slack 傳送連結、 Skype 等，可與您想要邀請。 在瀏覽器中開啟連結，可讓它們加入共同作業工作階段共用資料夾、 專案或開啟方案的內容。 請注意，給定的層級存取 Live Share 工作階段可以提供給來賓**您應該只與您所信任之人員共用**和考慮透過您共用的影響。

> **安全性秘訣：** 想要了解安全性含意，Live Share 功能嗎？ 請參閱[安全性](../reference/security.md)文章。

如果您受邀來賓有問題，[快速入門：加入您的第一個工作階段](join.md)文章上啟動並執行以來賓身分提供更多的資訊。

## <a name="8-optional-approve-the-guest"></a>8.[選擇性] 核准客體

根據預設，來賓會自動加入您的共同作業工作階段，並當他們準備好要與您合作，您會收到通知。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

您可以選擇改為加入的任何人都需要明確的 「 核准 」。 如果您有開啟此設定時，通知會提示您核准的客體，當他們嘗試加入您的工作階段。

請參閱[需要客體核准](../reference/security.md#requiring-guest-approval)如需有關如何開啟此功能。

## <a name="9-collaborate"></a>9.共同作業 ！

就這麼容易！ 以下是要試試看，一旦來賓已加入您的幾個事項：

1. 四處移動到不同的檔案，在專案中獨立並進行一些編輯
1. 請遵循來賓，並觀察它們捲動，進行編輯，然後瀏覽至不同的檔案
1. 啟動與他們共同偵錯工作階段
1. 共用伺服器，因此您可以看看起來像在其電腦上執行的 web 應用程式
1. 共用終端機，並執行一些命令

請參閱[Visual Studio Code](../use/vscode.md)並[Visual Studio](../use/vs.md)有關如何執行這些動作，以及其他資訊的延伸模組文件。

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。

## <a name="next-steps"></a>後續步驟

看看這些額外的文章，如需詳細資訊。

- [快速入門：加入您的第一個共同作業工作階段](join.md)
- [操作說明：使用 Visual Studio Code 進行共同作業](../use/vscode.md)
- [操作說明：使用 Visual Studio 進行共同作業](../use/vs.md)

參考資料

- [Live Share 的連線需求](../reference/connectivity.md)
- [Live Share 的安全性功能](../reference/security.md)
- [語言和平台支援](../reference/platform-support.md)
- [延伸模組支援](../reference/extensions.md)
