---
title: "The following components could not be browsed: | Microsoft Docs"
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
  - "VS_E_CANNOTBROWSECOM"
  - "VS.Message.0x00006A6D"
  - "VS_E_LOADTYPELIBFAILED"
  - "VS_E_INVALIDCOMCOMPONENT"
  - "VS_E_UNRECOGNIZEDCOMPONENT"
  - "VS.Message.0x00006A6E"
  - "VS.Message.ObjectBrowserErrors"
  - "vs.Message.0x00005AC3"
  - "VS.Message.0x00005AC4"
  - "VS.Message.0x00005AC5"
  - "VS_E_REGFAILEDCOMCOMPONENT"
ms.assetid: 83b03767-eecb-47a4-8029-166308c7dded
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The following components could not be browsed:
이 메시지 상자에는 개체 브라우저 및 구성 요소 선택 대화 상자와 관련된 여러 오류가 나열될 수 있습니다.  다음은 가장 일반적으로 발생하는 몇 가지 오류입니다.  
  
## 개체 브라우저에서 구성 요소 또는 파일 형식을 볼 수 없습니다.  
 이 오류는 존재하지 않거나 올바르지 않은 파일 이름을 지정하거나 개체 브라우저를 통해 찾을 수 없는 파일을 지정할 경우 일반적으로 발생합니다.  
  
#### 이 오류를 해결하려면  
  
-   지정한 파일 이름이 존재하고 .NET 어셈블리, COM 형식 라이브러리 또는 소스 브라우저 파일과 같은 검색 가능한 구성 요소인지 확인합니다.  
  
## 파일이 올바른 .NET Framework 또는 COM 구성 요소가 아닙니다.  
 이 오류는 지정된 구성 요소가 .NET Framework 어셈블리 또는 COM 형식 라이브러리가 아닌 경우 일반적으로 발생합니다.  
  
#### 이 오류를 해결하려면  
  
-   검색할 다른 구성 요소를 선택합니다.  
  
## 파일을 COM 구성 요소로 등록할 수 없습니다.  
 이 오류는 COM 구성 요소의 형식 라이브러리를 등록할 수 없는 경우 일반적으로 발생합니다.  형식 라이브러리가 없거나 손상되었을 수 있습니다.  
  
#### 이 오류를 해결하려면  
  
-   구성 요소를 다시 설치하고 다시 시도합니다.  
  
## 일치하는 형식 라이브러리를 등록하지 않았거나 등록된 정보가 올바르지 않습니다.  
 지정한 형식 라이브러리가 없거나 올바른 정보를 포함하지 않을 수 있습니다.  
  
#### 이 오류를 해결하려면  
  
-   형식 라이브러리가 있고 제대로 등록되었는지 확인합니다.  
  
## COM 형식 라이브러리를 검색하는 데 필요한 구성 요소가 없거나 제대로 등록되지 않았습니다.  
 vstlbinf.dll 파일이 없거나 잘못 등록되었습니다.  
  
#### 이 문제를 해결하려면  
  
1.  컴퓨터에서 vstlbinf.dll을 찾고 regsvr32.exe를 사용하여 등록합니다.  
  
     — 또는 —  
  
2.  컴퓨터에서 vstlbinf.dll을 찾을 수 없으면 이 제품을 다시 설치합니다.  
  
## 참고 항목  
 [Object Browser](http://msdn.microsoft.com/ko-kr/f89acfc5-1152-413d-9f56-3dc16e3f0470)   
 [Edit Custom Component Set Dialog Box](http://msdn.microsoft.com/ko-kr/dc995bd7-afbf-4389-ba1c-f377b677ded7)