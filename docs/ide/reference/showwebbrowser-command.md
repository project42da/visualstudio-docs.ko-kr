---
title: "ShowWebBrowser 명령 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4a54023892d1432639fd1211273195b941e8f081
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="showwebbrowser-command"></a>웹 브라우저 표시 명령
IDE(통합 개발 환경) 내부 또는 외부의 웹 브라우저 창에서 지정하는 URL을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
View.ShowWebBrowser URL [/new][/ext]  
```  
  
## <a name="arguments"></a>인수  
 `URL`  
 필수 요소. 웹 사이트의 URL(Uniform Resource Locator)입니다.  
  
## <a name="switches"></a>스위치  
 /new  
 선택 사항입니다. 웹 브라우저의 새 인스턴스에서 페이지가 표시되도록 지정합니다.  
  
 /ext  
 선택 사항입니다. IDE 외부의 기본 웹 브라우저에 페이지가 표시되도록 지정합니다.  
  
## <a name="remarks"></a>설명  
 **ShowWebBrowser** 명령의 별칭은 **navigate** 또는 **nav**입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 IDE 외부의 웹 브라우저에서 MSDN Online 홈페이지를 표시합니다. 웹 브라우저의 인스턴스가 이미 열린 경우 사용되고, 그렇지 않으면 새 인스턴스가 시작됩니다.  
  
```  
>View.ShowWebBrowser http://msdn.microsoft.com /ext  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)