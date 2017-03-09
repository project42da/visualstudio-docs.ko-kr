---
title: "예외 문제 해결: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Microsoft.VisualStudio.Tools.Applications.Runtime.ControlNotFoundException 예외"
ms.assetid: d780b8cc-c3f1-45ed-8f8e-3f8728a4b770
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException
<xref:Microsoft.VisualBasic.FileIO.MalformedLineException> 예외는 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>가 지정된 형식을 사용하여 행을 구문 분석할 수 없는 경우 throw됩니다.  
  
 이 예외 개체의 `Error Line` 속성에는 오류의 원인이 된 줄의 텍스트가 포함됩니다.  
  
## 관련 팁  
 **TextFieldType 및 Delimiter 매개 변수가 제대로 정의되어 있는지 확인하십시오.**  
 `TextFieldType`\(구분 또는 고정 폭\)은 파일의 형식과 일치해야 합니다.`TextFieldType`이 `FixedWidth`인 경우 `FieldWidths` 속성이 올바르게 설정되어 있는지 확인합니다.`TextFieldType`이 `Delimited`인 경우 `Delimiters` 속성이 올바르게 설정되어 있는지 확인합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 [Parsing Text Files with the TextFieldParser Object](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object)   
 [How to: Read From Comma\-Delimited Text Files](../Topic/How%20to:%20Read%20From%20Comma-Delimited%20Text%20Files%20in%20Visual%20Basic.md)   
 [How to: Read From Fixed\-width Text Files](../Topic/How%20to:%20Read%20From%20Fixed-width%20Text%20Files%20in%20Visual%20Basic.md)