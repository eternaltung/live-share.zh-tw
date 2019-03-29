---
title: 使用者設定檔-Visual Studio 即時共用 |Microsoft Docs
description: 如何檢視並移除您的 Visual Studio Live Share 使用者設定檔的概觀。
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 38fb6fada1030bddac8f3437f19f0ae259f5626e
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640025"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>使用者設定檔

當您使用 Visual Studio Live Share 進行驗證時，它會建立使用者設定檔，可讓您與共同作業以查看您屬於任何參與者 （例如您的電子郵件地址、 虛擬人偶）。 在任何時候，您可以檢視 Live Share 已代替您儲存瀏覽至下列頁面 （取決於您所使用的身分識別提供者） 的其中一個設定檔資訊：

- [Microsoft Account / Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

頁面會要求您登入若要確認您的身分識別，並且顯示您的使用者設定檔的原始 JSON 輸出。

<img width="500px" src="media/user-profile.png" />

如果 Visual Studio Live Share 目前沒有您用以登入的身分識別儲存的設定檔，然後它會讓您也知道。

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>移除您的設定檔

如果您想要移除您的使用者設定檔，您可以按一下標題為的連結`Click here to get your data removed from our systems`上[使用者設定檔頁面](#user-profile)。 或者，您可以瀏覽下列頁面直接 （取決於您所使用的身分識別提供者） 的其中一個：

- [Microsoft Account / Azure Active Directory](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

否則，Visual Studio Live Share 將自動刪除您的設定檔的 30 天後您上次成功登入。 在此情況下，「 成功登入 」 是指下列 （取決於您使用的工具）：

| IDE/編輯器 | 您的使用者設定檔將會刪除 30 天之後上一次您... |
|-|-|
| Visual Studio | 啟動 IDE 的新執行個體。 若要支援單一登入，Visual Studio Live Share 重新整理驗證工作階段每次您開啟 Visual Studio 的新執行個體。 |
| Visual Studio Code | 完成瀏覽器為基礎的驗證工作流程 (例如按一下`Sign In`按鈕，或執行`Live Share: Sign in with browser`命令)。 Visual Studio Live Share 會記住您在用戶端，以防止您不需要登入每次您共用的驗證工作階段。 不過，該工作階段會在 30 天後到期，而且永遠不會自動重新整理，直到您明確重新登入透過瀏覽器。 |

## <a name="see-also"></a>另請參閱

- [語言和平台支援](reference/platform-support.md)
- [Live Share 的連線需求](reference/connectivity.md)
- [Live Share 的安全性功能](reference/security.md)
- [所有主要 Bug、功能要求和限制](https://aka.ms/vsls-issues) \(英文\)
- [所有功能要求和限制](https://aka.ms/vsls-feature-requests) \(英文\)

有問題嗎？ 請參閱[疑難排解](troubleshooting.md)或[提供意見反應](support.md)。
