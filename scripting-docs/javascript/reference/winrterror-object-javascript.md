---
title: "WinRTError 개체(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "JavaScript, WinRTError 개체"
  - "WinRTError 개체[JavaScript]"
ms.assetid: d75ab8e5-e729-4d86-90fd-ea228c30dd66
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# WinRTError 개체(JavaScript)
Windows 런타임 호출 시 오류를 나타내는 HRESULT가 반환되면 JavaScript는 해당 HRESULT를 특수한 Windows 런타임 오류로 변환합니다.  이 오류는 Windows 런타임을 사용할 수 있을 때 전역 JavaScript 네임스페이스의 일부분으로 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서만 사용 가능합니다.  
  
## 구문  
  
```  
  
errorObj = new WinRTError();   
```  
  
## 설명  
 WinRTError 오류 유형은 Windows 런타임 API에서 발생하는 오류에만 사용됩니다.  
  
## 예제  
 다음 예에서는 WinRTError가 throw 및 catch되는 방식을 보여 줍니다.  
  
```javascript  
try {  
            Windows.Storage.ApplicationData.localFolder.createFileAsync("sample.txt");  
        } catch (err) {  
            var n = err;  
        }  
  
```  
  
## 메서드  
 WinRTError 개체에는 메서드가 없습니다.  
  
## 속성  
 WinRTError 개체의 속성은 [Error 개체](../../javascript/reference/error-object-javascript.md) 개체와 동일합니다.  
  
## 요구 사항  
 WinRTError 개체는 [!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서만 지원되며 Internet Explorer에서는 지원되지 않습니다.  
  
## 참고 항목  
 [Error 개체](../../javascript/reference/error-object-javascript.md)