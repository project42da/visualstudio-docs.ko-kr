---
title: "Error copying the application configuration file to the run directory. &lt;reason&gt; | Microsoft Docs"
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
  - "vs.tasklisterror.cant_copy_appcfg_file"
ms.assetid: 15699a76-16ef-40a8-8ed4-5eef4d2c0e72
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Error copying the application configuration file to the run directory. &lt;reason&gt;
프로젝트 시스템에서 프로젝트를 실행할 디렉터리에 app.config 파일을 복사할 수 없습니다.  이 오류가 발생하면 빌드 프로세스는 실패합니다.  
  
 이 오류는 .exe 파일을 빌드할 때만 발생합니다.  
  
 빌드 시스템은 프로젝트의 루트 폴더에서 app.config라는 파일을 찾습니다.  그런 다음 이 파일이 프로젝트의 출력 디렉터리에 복사됩니다. 출력 디렉터리에서 이 파일의 이름은 *outputfile.*config입니다.  
  
 이 오류가 발생하는 이유는 다음과 같습니다.  
  
-   디스크 공간이 부족합니다.  
  
-   MAX\_PATH를 초과했습니다.  
  
 실행 중인 응용 프로그램의 다른 복사본이 없는지도 확인하십시오.  
  
## 참고 항목  
 [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)