---
title: "Windows 런타임 DateTime 및 TimeSpan 표현 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DateTime[JavaScript]"
  - "JavaScript, Windows 런타임 날짜 및 시간"
  - "TimeSpan[JavaScript]"
ms.assetid: 9743e9ac-9054-463e-8264-427183e4905f
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# Windows 런타임 DateTime 및 TimeSpan 표현
날짜 및 시간의 JavaScript 표현은 Windows 런타임 버전과 다릅니다.  Windows 런타임 [DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx) 구조는 JavaScript에서 `DateTime` 데이터를 일치시키는 백업 저장소가 있고 JavaScript `Date`와 범위 및 전체 자릿수가 다른 [Date](../javascript/reference/date-object-javascript.md)로 표현됩니다.  이 사용자 지정 `Date` 개체를 수정하면 표준 JavaScript `Date`가 되고 전체 자릿수가 손실됩니다.  JavaScript `Date` 값은 Windows 런타임 `DateTime`에 전달될 수 있으며 범위가 검사되어 마샬링 예외가 발생할 수 있습니다.  
  
 Windows 런타임 [TimeSpan](http://msdn.microsoft.com/ko-kr/c5defb66-819c-4796-85b5-07ed249a5d86) 구조는 밀리초로 변환되고 JavaScript 숫자로 반환됩니다.  
  
## 참고 항목  
 [JavaScript에서 Windows 런타임 사용](../jswinrt/using-the-windows-runtime-in-javascript.md)