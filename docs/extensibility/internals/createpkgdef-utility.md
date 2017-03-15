---
title: "CreatePkgDef 유틸리티 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "패키지 정의"
  - "pkgdef 만들기"
  - "pkgdef"
  - "createpkgdef"
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# CreatePkgDef 유틸리티
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

매개 변수로 Visual Studio 확장에 대 한.dll 파일을 사용 하 고.dll을 함께.pkgdef 파일을 만듭니다. .Pkgdef 파일은 그렇지 않으면 레지스트리에 쓸 수는 시스템 확장을 설치할 때 모든 정보를 포함 합니다.  
  
> [!NOTE]
>  자동으로 Visual Studio SDK에 포함 된 프로젝트 템플릿 중 대부분은 빌드 프로세스의 일부로.pkgdef 파일을 만듭니다. 이 문서는 사용자에 게 패키지를 수동으로 만들거나.pkgdef 배포를 사용 하 여 기존 패키지를 변환 하려고 합니다.  
  
## 구문  
  
```  
CreatePkgDef /out=FileName [/codebase] [/assembly] AssemblyPath  
```  
  
## 인수  
 \/ \= 아웃`FileName`  
 필수 요소. .Pkgdef 출력 파일의 이름을 설정```FileName`합니다.  
  
 \/codebase  
 선택적 요소. 코드 베이스 유틸리티로 강제로 등록 합니다.  
  
 \/assembly  
 어셈블리 유틸리티로 강제로 등록 합니다.  
  
 `AssemblyPath`  
 .pkgdef 생성 하려는.dll 파일의 경로입니다.  
  
## 설명  
 .Pkgdef 파일을 사용 하 여 확장 배포에는 이전 버전의 Visual Studio의 레지스트리 요구 사항을 대체 합니다.  
  
 .Pkgdef 파일은 다음 위치 중 하나에 설치 해야 합니다. %localappdata%\\Microsoft\\Visual Studio\\14.0\\Extensions\\ 또는 %vsinstalldir%\\Common7\\IDE\\Extensions\\ 합니다. 설치 폴더 %localappdata%\\Microsoft\\Visual Studio\\14.0\\Extensions\\ 이면 확장 Visual Studio에서 인식 됩니다 하지만 기본적으로 비활성화 됩니다. 사용자는 사용 하 여 확장 가능 **확장 및 업데이트**합니다. 설치 폴더 %vsinstalldir%\\Common7\\IDE\\Extensions\\ 이면 확장은 기본적으로 사용 됩니다.  
  
> [!NOTE]
>  **확장 및 업데이트** VSIX 패키지의 일부로 설치 되어 있지 않으면 확장 프로그램에 액세스 하는 도구를 사용할 수 없습니다.  
  
## 참고 항목  
 [CreateExpInstance 유틸리티](../../extensibility/internals/createexpinstance-utility.md)