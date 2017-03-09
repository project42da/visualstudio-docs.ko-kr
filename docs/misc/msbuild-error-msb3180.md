---
title: "MSBuild 오류 MSB3180 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.DuplicateComDefinition"
helpviewer_keywords: 
  - "MSB3180"
ms.assetid: 98d8cb76-6176-4121-82ee-8a297d9deebc
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3180
**MSB3180: COM 구성 요소 '\<assembly\>'이\(가\) '\<file\>'과\(와\) '\<file\>' 둘 다에 정의되었습니다\(clsid\/tlbid\="'\<assembly\>'"\).**  
  
 이 오류는 응용 프로그램 매니페스트를 생성하는 동안 파일 참조나 종속된 매니페스트에서 \(클래스 또는 형식 라이브러리에 대한\) 중복된 COM 참조를 발견한 경우 발생합니다.  
  
 예를 들어, 외부 매니페스트가 있는 COM 개체에 대한 참조를 추가하고 내부 매니페스트가 있는 동일한 COM 개체에 대한 참조를 추가한 경우 이 오류가 발생할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   중복된 COM 참조 중 하나를 제거합니다.  
  
## 참고 항목  
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)