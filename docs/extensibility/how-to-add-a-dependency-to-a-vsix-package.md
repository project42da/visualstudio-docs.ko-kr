---
title: "방법: VSIX 패키지에 대 한 종속성 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "패키지 참조"
  - "패키지 어셈블리"
  - "패키지 dll"
  - "vsix 참조"
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: VSIX 패키지에 대 한 종속성 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이미 대상 컴퓨터에 존재 하지 않는 모든 종속성을 설치 하는 VSIX 패키지 배포를 설정할 수 있습니다. 이를 위해 VSIX 종속성 source.extension.vsixmanifest 파일에 포함 됩니다.  
  
#### 종속성을 추가 하려면  
  
1.  source.extension.vsixmanifest 파일을 열고는 **디자인** 보기. 이동는 **종속성** 탭을 클릭 **새로**합니다.  
  
2.  설치 된 확장을 추가 하려면:에 **새 종속성 추가** 대화 상자에서 **확장을 설치** 을 선택한는 **이름**, 목록에서 확장을 선택 합니다.  
  
3.  설치 되어 있지 않은 다른 VSIX를 추가 하려면::에 **새 종속성 추가** 대화 상자에서 **파일 시스템에서 파일** 다음 사용 하 여는 **찾아보기** VSIX를 선택 하는 단추입니다.  
  
## 참고 항목  
 [VSIX 확장 1.0 스키마 참조](http://msdn.microsoft.com/ko-kr/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [VSIX 패키지에 대 한 분석](../extensibility/anatomy-of-a-vsix-package.md)   
 [Windows Installer 배포에 대 한 확장을 준비 하는 중](../extensibility/preparing-extensions-for-windows-installer-deployment.md)