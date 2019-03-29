---
title: 手動聯結-Visual Studio Live Share |Microsoft Docs
description: 在 Visual Studio Live 手動加入共同作業工作階段的詳細資訊共用。
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
ms.openlocfilehash: 8ec4bac1c169c17de5e5ec8d26352cc13d62683b
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640064"
---
# <a name="join-a-session-manually"></a>以手動方式加入工作階段

除了在瀏覽器中聯結的共同作業工作階段中開啟連結，您可以手動聯結將連結貼到已在執行的工具。 這可以是很有用，如果您想要使用不同的工具，比平常，或如果您有問題取得邀請連結至基於某些原因的工作項目。

確切的指示而有所不同[Visual Studio](#join-from-visual-studio)並[Visual Studio Code](#join-from-visual-studio-code)，因此請選擇您想要使用的詳細資訊的工具。

## <a name="join-from-visual-studio-code"></a>從 Visual Studio 程式碼加入

### <a name="1-sign-in"></a>1.登入

>**注意：** 如果您想要加入共同作業工作階段為唯讀的來賓，您可以略過登入。 您將可以檢視與導覽共用的程式碼周圍的存取，但無法進行編輯。

![要求使用網頁瀏覽器登入的快顯通知](../media/vscode-sign-in-toast.png)

為了進行共同作業，您需要登入 Visual Studio Live Share，這樣每個人才都知道您的身分。 **按一下 [** "Live Share"狀態列的項目或按下**Ctrl + Shift + P / Cmd + Shift + P** ，然後選取 「 即時共用：使用瀏覽器登入] 命令。

![VS Code [登入] 按鈕](../media/vscode-sign-in-button.png)

通知會出現要求您登入的啟動時，將會啟動您的瀏覽器。 在瀏覽器中完成登入程序，完成後關閉瀏覽器。

如果您正在使用 VS Code 的問題並未在收取成功的登入，按一下瀏覽器中成功畫面中的"時遇到問題 」 連結，然後依照指示進行。 請參閱[疑難排解](../troubleshooting.md#sign-in)如需其他提示。

### <a name="2-use-the-join-command"></a>2.使用 [加入] 命令

在 VS Code 活動列中，開啟 Live Share viewlet，並選取 「 聯結共同作業工作階段...」圖示或項目。

![加入 viewlet 圖示](../media/vscode-join-viewlet.png)

>**注意：** 如果您要聯結為唯讀的來賓，則會要求您輸入顯示名稱，以協助您識別工作階段中的參與者。

### <a name="3-paste-the-invite-link"></a>3.貼上 [邀請] 連結

貼上您所送出，並按 'enter ' 鍵以確認邀請 URL。

就這麼容易！ 您應該很快就會連線到共同作業工作階段。

## <a name="join-from-visual-studio"></a>加入從 Visual Studio

### <a name="1-sign-in"></a>1.登入

安裝之後，請啟動 Visual Studio，然後登入，如果您尚未這麼做。 如果您要使用不同的登入 Visual Studio 比您[個人化帳戶](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio)，請前往**工具&gt;選項&gt;Live Share&gt;使用者帳戶**。

![與登入](../media/vs-sign-in-button.png)

仍然遇到問題嗎？ 請參閱[疑難排解](../troubleshooting.md#sign-in)。

### <a name="2-use-the-join-command"></a>2.使用 [加入] 命令

只要前往**檔案 > 加入共同作業工作階段**。

![VS 加入功能表](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3.貼上 [邀請] 連結

貼上您所送出，並按 'enter ' 鍵以確認邀請 URL。

就這麼容易！ 您應該很快就會連線到共同作業工作階段。

## <a name="see-also"></a>另請參閱

快速入門

- [快速入門：共用您的第一個專案](../quickstart/share.md)
- [快速入門：加入您的第一個工作階段](../quickstart/join.md)

做法

- [操作說明：使用 Visual Studio Code 共同作業](../use/vscode.md)
- [如何：使用 Visual Studio 共同作業](../use/vs.md)
- [操作說明：提供意見反應](../support.md)

參考資料

- [Live Share 的連線需求](connectivity.md)
- [Live Share 的安全性功能](security.md)
- [Linux 安裝詳細資料](linux.md)
- [語言和平台支援](platform-support.md)
- [延伸模組支援](extensions.md)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
