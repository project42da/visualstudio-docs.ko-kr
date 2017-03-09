---
title: "MSBuild 오류 MSB3152 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.PackageFileNotFound"
helpviewer_keywords: 
  - "MSB3152"
ms.assetid: 5a3859d4-4107-4e46-bb42-04de92b551de
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3152
**MSB3152: 필수 구성 요소의 설치 위치를 '구성 요소 공급업체의 웹 사이트'로 설정하지 않아 디스크에서 '\<package\>' 항목의 '\<file\>' 파일을 찾을 수 없습니다.  자세한 내용은 도움말을 참조하십시오.**  
  
 이 오류는 필수 구성 요소 설치 관리자에 필요한 파일이 없는 경우에 발생합니다.  설치 관리자 파일은 Visual Studio가 재배포 가능 패키지를 위해 예약한 특수 폴더로 이동합니다.  개발에 사용 중인 Visual Studio 버전에 따라 폴더가 달라집니다.  특수 폴더 위치에 대한 자세한 내용은 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
-   파일이 디스크에 있는지 확인합니다.  
  
-   HomeSite를 사용하여 패키지 문제를 해결해 봅니다.  
  
-   프로젝트 파일에서 `CopyComponents`를 `false`로 설정합니다.  
  
-   손상된 부트스트래퍼 패키지는 사용하지 않도록 합니다.  
  
## 참고 항목  
 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)