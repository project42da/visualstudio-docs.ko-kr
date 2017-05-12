---
title: "SOURCE_TEXT_ATTR 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "SOURCE_TEXT_ATTR 상수"
ms.assetid: 459384b0-1463-4841-a2b3-a993207163bf
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# SOURCE_TEXT_ATTR 열거형
단일 문자를 원본 텍스트의 특성을 설명 합니다.  
  
## 구문  
  
```cpp  
enum enum_SOURCE_TEXT_ATTR  
{  
    SOURCETEXT_ATTR_KEYWORD    = 0x0001,  
    SOURCETEXT_ATTR_COMMENT    = 0x0002,  
    SOURCETEXT_ATTR_NONSOURCE    = 0x0004,  
    SOURCETEXT_ATTR_OPERATOR   = 0x0008,  
    SOURCETEXT_ATTR_NUMBER    = 0x0010,  
    SOURCETEXT_ATTR_STRING    = 0x0020,  
    SOURCETEXT_ATTR_FUNCTION_START  = 0x0040  
};  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|SOURCETEXT\_ATTR\_KEYWORD|0x0001|문자 언어 키워드, 예를 들어, VBScript 키워드의 일부인 `While`.|  
|SOURCETEXT\_ATTR\_COMMENT|0x0002|문자 주석 블록의 일부입니다.|  
|SOURCETEXT\_ATTR\_NONSOURCE|0x0004|문자 컴파일된 언어 소스 텍스트의 일부가 아닙니다.  스크립트 블록을 둘러싼 예를 들어, HTML.|  
|SOURCETEXT\_ATTR\_OPERATOR|0x0008|문자 언어 연산자의 일부입니다.  예를 들어:, 산술 연산자  **\+**.|  
|SOURCETEXT\_ATTR\_NUMBER|0x0010|문자 상수 언어의 일부입니다.  예를 들어, 상수 3.14159입니다.|  
|SOURCETEXT\_ATTR\_STRING|0x0020|문자 언어 문자열 상수 부분입니다.  예를 들어, 문자열 "Hello World"입니다.|  
|SOURCETEXT\_ATTR\_FUNCTION\_START|0x0040|문자 함수 블록의 시작을 나타냅니다.|  
  
## 설명  
 일반적으로 `IDebugDocumentHost::GetScriptTextAttributes`, `IActiveScriptDebug::GetScriptletTextAttributes`, 및 `IActiveScriptDebug::GetScriptTextAttributes` 메서드는 텍스트 특성, 문자 당 반환 하지 않으면.  
  
-   GETATTRTYPE\_DEPSCAN 플래그 설정 된 경우 메서드는 SOURCETEXT\_ATTR\_IDENTIFIER 및 SOURCETEXT\_ATTR\_MEMBERLOOKUP 플래그를 반환할 수 있습니다,  
  
-   GETATTRFLAG\_THIS 플래그 설정 된 경우 메서드가 SOURCETEXT\_ATTR\_THIS 플래그를 반환할 수 있습니다,  
  
-   SOURCETEXT\_ATTR\_HUMANTEXT 플래그 경우에 메서드가 반환 된 GETATTRFLAG\_HUMANTEXT 플래그가 설정 됩니다.  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)