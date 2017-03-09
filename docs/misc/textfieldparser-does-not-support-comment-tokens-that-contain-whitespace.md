---
title: "TextFieldParser는 공백이 포함된 주석 토큰을 지원하지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_WhitespaceInToken"
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# TextFieldParser는 공백이 포함된 주석 토큰을 지원하지 않습니다.
공백이 포함된 주석 토큰이 제공되었습니다. 토큰의 시작 부분에 공백이 발생하지 않는 한 `TextFieldParser`는 공백을 포함하는 주석 토큰을 지원하지 않습니다. 토큰의 시작 부분에 있는 공백은 무시됩니다.  
  
### 이 오류를 해결하려면  
  
-   올바른 주석 토큰을 제공합니다.  
  
## 참고 항목  
 [TextFieldParser.CommentTokens 속성](http://msdn.microsoft.com/ko-kr/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)   
 [Parsing Text Files with the TextFieldParser Object](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object)   
 [TextFieldParser Object](/dotnet/visual-basic/language-reference/objects/textfieldparser-object)