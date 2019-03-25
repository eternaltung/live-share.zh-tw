---
title: 共用快速入門 - Visual Studio Live Share | Microsoft Docs
description: 使用 Visual Studio Live Share 共同作業工作階段來共用您第一個專案的概略逐步解說。
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
ms.translationtype: HT
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

準備好開始著手了嗎？  小組共同作業就應該如此快速且自然，且能輕鬆做到！ 因此，Visual Studio Live Share 可讓您輕鬆開始使用，以便您順暢地開始共用您的工作和想法。

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在這兩個執行個體使用相同的身分識別。 趕緊去瞧一瞧！

只要遵循下列步驟即可開始共用。

## <a name="1-install-the-extension"></a>1.安裝延伸模組

安裝延伸模組很簡單。 請遵循下列步驟進行：

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

安裝 Live Share 延伸模組、重新啟動並等待相依性完成安裝 (VS Code) 之後，您會想要登入以便其他參與者知道您是誰。 只需按一下 [Live Share] 狀態列項目 (VS Code)/[登入] 按鈕 (VS) 來開始。

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

在 **VS Code** 中，瀏覽器會在要求您登入的通知出現時啟動。 在瀏覽器中完成登入程序，完成後關閉瀏覽器。

![使用網頁瀏覽器要求您登入的快顯通知](../media/vscode-sign-in-toast.png)

> **Linux 使用者：** 如果您使用舊版 Live Share (v0.3.295 或更舊版本)，系統可能會提示您輸入使用者程式碼。 將延伸模組更新為最新版本，或在登入後按一下 [遇到問題了嗎?] 連結以查看程式碼。 請參閱[此處以取得詳細資料](../use/vscode.md#sign-in-using-a-user-code)。

在 **Visual Studio** 中，Live Share 會自動使用您的[個人化帳戶](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)。 如此一來，您即可直接以一般方式登入。 不過，如果您希望使用與 Visual Studio 個人化帳戶不同的登入方式，請前往 [工具] &gt; [選項] &gt; [Live Share] &gt; [使用者戶帳戶]，然後選取不同的認證。

如果仍然發生問題，請參閱[疑難排解](../troubleshooting.md#sign-in)。

## <a name="3-open-a-folder-project-or-solution"></a>3.開啟資料夾、專案或方案

使用您的一般工作流程來開啟資料夾、專案或您希望在 Visual Studio 或 Visual Studio Code 中共用的方案。

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [選擇性] 更新隱藏或排除的檔案

根據預設，Live Share 會**隱藏**來自來賓之共用資料夾中 .gitignore 檔案所參考的任何檔案/資料夾。 **隱藏**檔案可防止該檔案在來賓的檔案樹狀目錄中顯示。 **排除**檔案會套用更嚴格的規則，以防止 Live Share 在前往定義時，或您在偵錯中或「受到跟隨」時進入檔案等情況下，為來賓開啟該檔案。 如果您希望隱藏/排除不同的檔案，您可以使用這些設定將 **.vsls.json** 檔案新增至您的專案。 請參閱[控制檔案存取權和可見性](../reference/security.md#controlling-file-access-and-visibility)以取得詳細資料。

## <a name="5-start-a-collaboration-session"></a>5.開始共同作業工作階段

接下來，只需在工具中按一下 [Live Share]，邀請連結就會自動複製到剪貼簿。

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
> 桌面防火牆軟體可能會要求您允許 Live Share 代理程式在您第一次共用時開啟連接埠。 這完全是選擇性的，但是當您與一起工作的人員位於相同網路時，可提供安全的「直接模式」來改善效能。 請參閱[變更連線模式](../reference/connectivity.md#changing-the-connection-mode)以取得詳細資料。

## <a name="6-optional-enable-read-only-mode"></a>6. [選擇性] 啟用唯讀模式

一旦您啟動共同作業工作階段，您可以將工作階段設定為唯讀，以防止來賓對正在共用的程式碼進行編輯。

共用之後，您會收到通知指出邀請連結已複製到剪貼簿。 您隨即可以選取選項來將工作階段設為唯讀。

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

在 **VS Code** 中，您也可以從 [Live Share] viewlet 索引標籤啟動唯讀工作階段。

![使用網頁瀏覽器要求您登入的快顯通知](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7.將邀請連結傳送給某人

透過電子郵件、Slack、Skype 等將連結傳送給您希望邀請的人員。 在瀏覽器中開啟連結，可讓他們加入共用您所開啟之資料夾、專案或方案內容的共同作業工作階段。 請注意，考慮到 Live Share 工作階段所能為來賓提供的存取層級，**您應該只與您信任的人共用**，並考量共用這些內容的影響。

> **安全性提示：** 想要了解一些 Live Share 功能的安全性影響嗎？ 請參閱[安全性](../reference/security.md)一文。

如果您邀請的來賓有問題，[快速入門：加入您的第一個工作階段](join.md)一文提供以來賓身分啟動並執行的詳細資訊。

## <a name="8-optional-approve-the-guest"></a>8. [選擇性] 核准來賓

根據預設，來賓會自動加入您的共同作業工作階段，當他們準備好要與您共同作業時，您即會收到通知。

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

您可以選擇讓任何人在加入前都需要明確的「核准」。 如果您開啟此設定，則當來賓嘗試加入您的工作階段時，系統會通知您核准。

請參閱[要求來賓核准](../reference/security.md#requiring-guest-approval)以取得如何開啟此功能的詳細資料。

## <a name="9-collaborate"></a>9.共同作業！

就這麼容易！ 來賓加入您後，您可以嘗試下列一些事項：

1. 獨自瀏覽專案中的不同檔案，並進行一些編輯
1. 跟隨來賓，並觀察他們捲動、編輯並巡覽至不同檔案
1. 啟動與來賓的共同偵錯工作階段
1. 共用伺服器，以便您查看在其電腦上執行的 Web 應用程式
1. 共用終端機並執行一些命令

請參閱 [Visual Studio Code](../use/vscode.md) 和 [Visual Studio](../use/vs.md) 延伸模組文件，以取得如何執行這些動作及其他項目的資訊。

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。

## <a name="next-steps"></a>後續步驟

請查看下列其他文章以取得詳細資訊。

- [快速入門：加入您的第一個共同作業工作階段](join.md)
- [如何：使用 Visual Studio Code 共同作業](../use/vscode.md)
- [如何：使用 Visual Studio 共同作業](../use/vs.md)

參考資料

- [Live Share 的連線需求](../reference/connectivity.md)
- [Live Share 的安全性功能](../reference/security.md)
- [語言和平台支援](../reference/platform-support.md)
- [延伸模組支援](../reference/extensions.md)
