---
title: 加入快速入門-Visual Studio Live Share |Microsoft Docs
description: 第一個 Visual Studio Live Share 共同作業工作階段來聯結縮減逐步解說。
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
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255609"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>快速入門：加入您的第一個共同作業工作階段

> **注意：Visual Studio Live Share 目前為預覽狀態。使用者體驗和功能不是最終版本。**

歡迎使用 Visual Studio Live Share！ Live Share 可讓您即時與其他人以共同作業方式編輯和偵錯，不論您所使用程式設計語言或建置的應用程式類型為何。 它可讓您立即且安全地加入目前專案的小組，並視需要輸入偵錯工作階段，然後檢視和編輯終端機執行個體，請參閱 localhost web 應用程式、 聯結語音通話、 和更多功能 ！

準備好開始著手了嗎？ 因此快速且自然，就不難這麼做，應該是小組共同作業 ！ 基於這個理由，Visual Studio Live Share 可簡化開始使用，以便您可以無接縫地開始共用您的工作和想法。

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在這兩個執行個體上使用相同的身分識別。 趕緊去瞧一瞧！

只要遵循下列步驟來加入共同作業工作階段。

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
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
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

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2.[選擇性] 為唯讀的來賓，在 VS Code 中的聯結

在 VS Code 中，安裝 Live Share 延伸模組、 重新啟動，並等待相依性之後才能完成安裝，您可以開始，並加入共同作業工作階段為唯讀的來賓。

> [!NOTE]
> 如果您想要對您要加入的程式碼進行編輯，您必須[登入](../quickstart/join.md#3-Sign-in)。

開啟 （或重新開啟） 瀏覽器中的 [邀請] 連結，您會收到通知，在瀏覽器會想要啟動 VS Code。 讓它啟動，並先連接到共同作業工作階段。

當啟動 VS Code 時，您會收到快顯通知，要求您登入。 選取 繼續為唯讀的來賓 」 加入工作階段。

![加入做為唯讀客體快顯通知的工作階段](../media/vscode-read-only-guest.png)

系統會要求您輸入的顯示名稱，以協助您識別工作階段中的參與者。

![唯讀客體名稱](../media/vscode-read-only-guest-name.png)

之後，您會加入到工作階段為唯讀。 您將能夠檢視和巡覽程式碼、 共同的偵錯，以及檢視共用伺服器和終端機 （唯讀）。

> [!NOTE]
> 如果您想要稍後取得 讀取/寫入存取權的程式碼，您可以登入。 按一下您的顯示名稱狀態、 在列中，選取選項 [登入]。
![唯讀的訪客登入](../media/vscode-read-only-guest-signin.png)這樣就會啟動瀏覽器中，而且您可以選擇 Microsoft 或 GitHub 帳戶來登入。

## <a name="3-sign-in"></a>3.登入

安裝 Live Share 延伸模組、 重新啟動，並等待相依性，以完成安裝 (VS Code) 之後, 您會想要讓其他參與者了解您的身分登入。 如果您略過此步驟中，您會要求聯結過程中，登入，或可以加入工作階段為唯讀的來賓。 按一下 「 共用 」 狀態列項目 (VS Code) / 登入 按鈕 (VS) 開始。

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

在  **VS Code**，通知會出現要求您登入的啟動時，將會啟動您的瀏覽器。 完成登入您的瀏覽器中的程序，然後只需關閉瀏覽器完成。

![使用網頁瀏覽器登入要求的快顯通知](../media/vscode-sign-in-toast.png)

> **Linux 使用者：** 您可能會提示您輸入使用者程式碼，如果您使用較舊版本的 Live Share (v0.3.295 或以下版本)。 更新延伸模組的最新版本，或按一下 「 需要疑難排解嗎？ 」 連結登入之後，以查看程式碼。 請參閱[如需詳細資訊，這裡](../use/vscode.md#sign-in-using-a-user-code)。

在  **Visual Studio**，Live Share 會自動使用您[個人化帳戶](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)。 如此一來，您可以直接登入可以用正常方式。 不過，如果您不希望使用不同登入與您的 Visual Studio 個人化帳戶，請移至**工具&gt;選項&gt;Live Share&gt;使用者帳戶**並選取不同的認證。

請參閱[疑難排解](../troubleshooting.md#sign-in)如果仍然發生問題。

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4.開啟/重新-open 邀請連結在瀏覽器

現在，只要開啟 （或重新開啟） 瀏覽器中的 [邀請] 連結。

> **注意**：如果您尚未安裝 Live Share 延伸模組，您將會看到擴充功能市集的連結。 安裝擴充功能並重新啟動您的工具，然後重試。

您應該會收到通知，瀏覽器就會想要啟動已啟用 Live Share 工具。 如果您讓它啟動您所選的工具，您會連接到其啟動之後的共同作業工作階段。

![加入頁面](../media/join-page.png)

如果主機已離線，您會收到通知現在改為。 然後，您可以連絡主機，並要求他們再次共用。

> **疑難排解秘訣：** 當使用 VS Code，是確定您已**至少一次啟動此工具**安裝延伸模組並等候相依性，以完成安裝之後 （請參閱 [狀態] 列） 之前開啟/重新-opening [邀請] 頁面。 仍然有問題嗎？ 請參閱[手動聯結](../reference/manual-join.md)如需詳細資訊。

## <a name="5-collaborate"></a>5.共同作業 ！

就這麼容易！ 幾分鐘後，您會連接到您的同事共同作業工作階段。 根據預設，主應用程式自動接受加入，但主機已設定最多的人[需要客體核准](../reference/security.md#requiring-guest-approval)您將看到狀態列 / 加入 Live Share 正在等候核准您的要求，以加入主機上的對話方塊值得一提。

> **安全性秘訣：** 為來賓加入共同作業工作階段，請務必了解主機可能會針對您的存取權限制至特定檔案或功能。 想要了解一些 Live Share 功能和設定的安全性含意？ 請參閱[安全性](../reference/security.md)文章。

以下是嘗試幾件事：

1. 獨立專案四處移動，並進行某些編輯
2. 查看適用於 JavaScript、 TypeScript、 使用 intellisense 和/或C#程式碼
3. 編輯項目與主應用程式
4. 請依照下列主機，並瀏覽並在不同的檔案進行編輯，四處移動與其
5. 啟動與主應用程式的共同偵錯工作階段
6. 要求者共用的伺服器，因此您可以看看起來像在其電腦上執行的 web 應用程式
7. 要求者共用終端機，並執行一些命令

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。

## <a name="next-steps"></a>後續步驟

看看這些額外的文章，如需詳細資訊。

- [快速入門：共用您的第一個專案](share.md)
- [操作說明：使用 Visual Studio Code 進行共同作業](../use/vscode.md)
- [操作說明：使用 Visual Studio 進行共同作業](../use/vs.md)

參考資料

- [Live Share 的連線需求](../reference/connectivity.md)
- [Live Share 的安全性功能](../reference/security.md)
- [語言和平台支援](../reference/platform-support.md)
- [延伸模組支援](../reference/extensions.md)
