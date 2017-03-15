---
title: "Resource transformation for file &#39;file&#39; failed. &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.resx_generator_failed"
ms.assetid: 6b537d38-1da9-4f5f-9ae9-1f26e260c2ac
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Resource transformation for file &#39;file&#39; failed. &lt;reason&gt;
.resx 파일을 이진 .resources 파일로 변환하는 데 사용한 리소스 처리기에 오류가 발생했습니다.  구체적인 이유\(있는 경우\)는 문자열 끝에 추가됩니다.  이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
 이 오류는 주로 잘못된 .resx 파일로 인해 발생합니다.  예를 들어, 텍스트 편집기에서 파일을 열고 수정한 경우가 이에 해당합니다.  
  
 \<reason\>이 "항목이 이미 추가되었습니다.  사전에 있는 키: 'NewControlName.\<Property Name\>' 추가되는 키: 'ControlName.\<Property Name\>'"이면 다음 단계를 따라 오류를 재현하고 수정합니다.  
  
### 이 오류를 재현하려면  
  
1.  새 Windows 응용 프로그램을 만듭니다.  기본적으로는 Form1이 만들어집니다.  
  
2.  **보기** 메뉴에서 **속성**을 클릭합니다.  
  
3.  **속성** 창에서 **Localizable** 속성을 `True`로 설정합니다.  
  
4.  **속성** 창에서 **언어**를 클릭한 다음 값을 "Japanese"로 설정합니다.  
  
5.  도구 상자에서 단추를 폼으로 끌어 옵니다.  
  
6.  단추 이름을 "Button1"에서 "BUTTON1"로 변경합니다.  
  
7.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
### 이 오류를 해결하려면  
  
1.  **파일** 메뉴에서 **열기**를 가리킨 다음 **파일**을 클릭합니다.  
  
2.  Form1.resx 파일을 찾은 다음 **확인**을 클릭합니다.  Form1.resx가 표시됩니다.  
  
3.  원래 키 값을 찾은 다음 데이터 목록에서 직접 삭제합니다.  예를 들어, "Button1"이라는 단추가 있습니다.  이 단추 이름을 "BUTTON1"로 수정합니다.  "Button1"과 "BUTTON1"에 대한 키 값이 Form1.resx에 있습니다.  "Button1"의 모든 항목을 제거한 다음 프로젝트를 다시 빌드합니다.  
  
## 참고 항목  
 [Resources in .Resx File Format](http://msdn.microsoft.com/ko-kr/0c476133-87e4-47e8-b0ef-4b88f4ef3dc5)   
 [File Types and File Extensions in Visual Basic and Visual C\#](http://msdn.microsoft.com/ko-kr/f793852c-da06-4d52-a826-65f635844772)