---
title: "제거 ~ SAK 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "임시 파일"
  - "~ sak 파일"
  - "소스 제어 플러그 인, ~ SAK 파일"
ms.assetid: 5277b5fa-073b-4bd1-8ba1-9dc913aa3c50
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 제거 ~ SAK 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 API 1.2에는 ~ SAK 파일이 기능 플래그와 바뀌었습니다 플러그 인 MSSCCPRJ 파일 및 공유 체크 아웃을 지원 하는지 여부를 감지 하는 새 함수에서.  
  
## ~ SAK 파일이  
 Visual Studio.Net 앞에 임시 파일을 만들 ~ SAK.  이러한 파일 사용 하 여 플러그 인을 지원 하는지 확인 합니다.  
  
-   MSSCCPRJ입니다.소스 코드 제어 파일입니다.  
  
-   다중 체크 아웃 \(공유\)입니다.  
  
 소스 제어 플러그 인 API 1.2에서 제공 하는 고급 기능을 지 원하는 플러그인에 대 한 새로운 기능, 플래그 및 다음 섹션에서 자세히 설명 하는 기능을 사용 하 여 임시 파일을 만들지 않고 이러한 기능은 IDE를 감지할 수 있습니다.  
  
## 새 기능 플래그  
 `SCC_CAP_SCCFILE`  
  
 `SCC_CAP_MULTICHECKOUT`  
  
## 새 함수  
 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md)  
  
 [SccIsMultiCheckoutEnabled](../../extensibility/sccismulticheckoutenabled-function.md)  
  
 플러그 인 \(공유\) 다중 체크 아웃을 지원 하 고 해당 변수를 선언 하는 경우는 `SCC_CAP_MULTICHECKOUT` 기능 및 구현에서 `SccIsMultiCheckOutEnabled` 함수입니다.  이 함수는 소스 제어 프로젝트에서 체크 아웃 작업 발생 될 때마다 호출 됩니다.  
  
 플러그 인을 만들고 사용 하는 MSSCCPRJ의 지.SCC 파일을 다음이 선언는 `SCC_CAP_SCCFILE` 기능 및 구현에서 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md).  이 함수는 파일의 목록과 함께 호출 됩니다.  함수 반환 `TRUE/FALSE` Visual Studio MSSCCPRJ를 사용 해야 하는지 여부를 지정 하려면 각 파일에 대 한.이 대 한 소스 코드 제어 파일입니다.  소스 제어 플러그 인이 새 기능 및 함수를 지원 하기로 선택 하면 이러한 파일의 생성을 사용 하지 않도록 설정 하려면 다음 레지스트리 키를 사용할 수 있습니다.  
  
 \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0\\SourceControl\] "DoNotCreateTemporaryFilesInSourceControl" dword:00000001 \=  
  
> [!NOTE]
>  Dword:00000000에이 레지스트리 키를 설정 하면 존재 하지 않는, 하 키에 해당 하는 한 Visual Studio 여전히 임시 파일을 만들 시도 합니다.  그러나 레지스트리 키 dword:00000001을 설정 하면 Visual Studio 임시 파일을 만들 시도 하지 않습니다.  대신 소스 제어 플러그 인은 MSSCCPRJ를 지원 하지 않습니다 가정 합니다.SCC 파일이 공유 체크 아웃을 지원 하지 않습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)