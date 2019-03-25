---
title: 加入快速入門 - Visual Studio Live Share | Microsoft Docs
description: 加入您第一個 Visual Studio Live Share 共同作業工作階段的概略逐步解說。
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
ms.translationtype: HT
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

歡迎使用 Visual Studio Live Share！ Live Share 可讓您即時與其他人以共同作業方式編輯和偵錯，不論您所使用程式設計語言或建置的應用程式類型為何。 也可讓您立即且安全地加入小組成員的專案，然後視需要進入偵錯工作階段、檢視並編輯終端機執行個體、查看 localhost Web 應用程式、加入語音通話等！

準備好開始著手了嗎？ 小組共同作業就應該如此快速且自然，且能輕鬆做到！ 因此，Visual Studio Live Share 可讓您輕鬆開始使用，以便您順暢地開始共用您的工作和想法。

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在這兩個執行個體上使用相同的身分識別。 趕緊去瞧一瞧！

只要遵循下列步驟即可加入共同作業工作階段。

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

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [選擇性] 在 VS Code 中作為唯讀來賓加入

在 VS Code 中安裝 Live Share 延伸模組、重新啟動並等待相依性完成安裝後，您即可作為唯讀來賓加入共同作業工作階段。

> [!NOTE]
> 如果您希望對您要加入的程式碼進行編輯，您必須[登入](../quickstart/join.md#3-Sign-in)。

開啟 (或重新開啟) 瀏覽器中的邀請連結，您會收到瀏覽器想要啟動 VS Code 的通知。 讓其啟動，即會連線至共同作業工作階段。

啟動 VS Code 時，您會收到快顯通知，要求您登入。 選取 [以唯讀來賓身分繼續] 加入工作階段。

![以唯讀來賓身分加入工作階段快顯通知](../media/vscode-read-only-guest.png)

系統會要求您輸入顯示名稱，以協助工作階段中的參與者識別您。

![唯讀來賓名稱](../media/vscode-read-only-guest-name.png)

之後，您即會作為唯讀來賓加入工作階段。 您將能夠檢視和巡覽程式碼、共同偵錯、檢視共用伺服器和終端機 (唯讀)。

> [!NOTE]
> 如果您希望稍後取得對程式碼的讀取/寫入存取權，您可以登入。 在狀態列按一下您的顯示名稱，選取 [登入] 選項。
![唯讀來賓登入](../media/vscode-read-only-guest-signin.png)這會啟動您的瀏覽器，您可以選擇使用 Microsoft 或 GitHub 帳戶來登入。

## <a name="3-sign-in"></a>3.登入

安裝 Live Share 延伸模組、重新啟動並等待相依性完成安裝 (VS Code) 之後，您會想要登入以便其他參與者知道您是誰。 如果您略過此步驟，系統會要求您在加入程序中登入，或作為唯讀來賓加入工作階段。 按一下 [共用] 狀態列項目 (VS Code)/[登入] 按鈕 (VS) 來開始。

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

在 **VS Code** 中，瀏覽器會在要求您登入的通知出現時啟動。 在瀏覽器中完成登入程序，完成後關閉瀏覽器。

![使用網頁瀏覽器要求您登入的快顯通知](../media/vscode-sign-in-toast.png)

> **Linux 使用者：** 如果您使用舊版 Live Share (v0.3.295 或更舊版本)，系統可能會提示您輸入使用者程式碼。 將延伸模組更新為最新版本，或在登入後按一下 [遇到問題了嗎?] 連結以查看程式碼。 請參閱[此處以取得詳細資料](../use/vscode.md#sign-in-using-a-user-code)。

在 **Visual Studio** 中，Live Share 會自動使用您的[個人化帳戶](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)。 如此一來，您即可直接以一般方式登入。 不過，如果您希望使用與 Visual Studio 個人化帳戶不同的登入方式，請前往 [工具] &gt; [選項] &gt; [Live Share] &gt; [使用者戶帳戶]，然後選取不同的認證。

如果仍然發生問題，請參閱[疑難排解](../troubleshooting.md#sign-in)。

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4.開啟/重新開啟瀏覽器中的邀請連結

現在，請開啟 (或重新開啟) 瀏覽器中的邀請連結。

> **注意**：如果您尚未安裝 Live Share 延伸模組，您將會看到延伸模組市集的連結。 安裝延伸模組並重新啟動您的工具，然後重試。

您應該會收到通知，指出瀏覽器想要啟動提供 Live Share 的工具。 如果您讓其啟動所選的工具，則在啟動後您將連線至共同作業工作階段。

![加入頁面](../media/join-page.png)

如果主持人已離線，則會改為在此時收到通知。 您即可以連絡主持人，並要求再次共用。

> **疑難排解提示：** 使用 VS Code 時，請確定在安裝延伸模組後**至少啟動一次工具**，並等待相依性完成安裝 (請參閱狀態列) 後，再開啟/重新開啟邀請頁面。 仍然遇到問題嗎？ 請參閱[手動加入](../reference/manual-join.md)以取得詳細資料。

## <a name="5-collaborate"></a>5.共同作業！

就這麼容易！ 一小段時間後，您就會連線至您同事的共同作業工作階段。 根據預設，主持人會自動接受人員加入，但如果主持人設定[需要來賓核准](../reference/security.md#requiring-guest-approval)，則您會看到狀態列/加入對話指出 Live Share 正在等待主持人核准您的加入要求。

> **安全性提示：** 作為來賓加入共同作業工作階段時，請務必了解主持人可能會限制您存取特定檔案或功能。 想要了解一些 Live Share 功能和設定的安全性影響嗎？ 請參閱[安全性](../reference/security.md)一文。

您可以嘗試下列一些事項：

1. 獨自瀏覽專案，並進行一些編輯
2. 查看適用於 JavaScript、TypeScript 和/或 C# 程式碼的工作 Intellisense
3. 與主持人一起編輯某些內容
4. 在主持人進行巡覽並在不同檔案中編輯時跟著一起進行
5. 啟動與主持人的共同偵錯工作階段
6. 要求主持人共用伺服器，以便您查看在其電腦上執行的 Web 應用程式
7. 要求主持人共用終端機並執行一些命令

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。

## <a name="next-steps"></a>後續步驟

請查看下列其他文章以取得詳細資訊。

- [快速入門：共用您的第一個專案](share.md)
- [如何：使用 Visual Studio Code 共同作業](../use/vscode.md)
- [如何：使用 Visual Studio 共同作業](../use/vs.md)

參考資料

- [Live Share 的連線需求](../reference/connectivity.md)
- [Live Share 的安全性功能](../reference/security.md)
- [語言和平台支援](../reference/platform-support.md)
- [延伸模組支援](../reference/extensions.md)
