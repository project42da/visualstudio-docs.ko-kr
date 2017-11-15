---
title: "비동기 Windows 런타임 메서드의 특수한 오류 속성 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 120d8f699c8bedd0fe5762300203c5d5ec18e73e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a>비동기 Windows 런타임 메서드의 특수한 오류 속성
호출 스택의 하위 위치에서 오류가 발생할 수 있으므로 JavaScript에서 비동기 Windows 런타임 메서드를 디버그하기가 어려울 수 있습니다. JavaScript `Error` 개체에는 앱을 디버그 모드에서 실행할 때 비동기 Windows 런타임 메서드에서 오류가 발생할 때만 표시되는 추가 속성이 있습니다.  
  
## <a name="special-error-properties"></a>특수 오류 속성  
 디버그 모드에서 실패한 Windows 런타임 비동기 작업으로 인해 발생한 오류 개체에는 다음 특수 속성이 있습니다.  
  
-   `asyncOpSource`(개체) 오류를 생성한 호출이 이루어진 원본 위치에 대한 정보를 가져옵니다. `asyncOpSource.originatingCall` 속성(문자열)은 비동기 작업을 시작한 사용자 코드의 위치를 표시합니다.  
  
-   asyncOpType(문자열)은 오류를 발생시키는 비동기 작업 유형의 이름을 가져옵니다.  
  
 비동기 작업 오류에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [프라미스로 오류를 처리하는 방법](https://msdn.microsoft.com/en-us/library/windows/apps/hh700337.aspx)  
  
-   [Windows 런타임 오류 문제 해결](http://msdn.microsoft.com/en-us/1ef7d7df-82ac-441d-8ad0-54ab1318de64)