---
title: "소스 제어 정보를 제거 합니다. Proj 하 고 있습니다. Sln 파일 | Microsoft Docs"
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
  - "소스 제어 플러그 인,.sln 및.proj 파일"
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 정보를 제거 합니다. Proj 하 고 있습니다. Sln 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

SCC 소스 제어 플러그 인 API 버전 1.2 정보를 MSSCCPRJ에 저장 됩니다.소스 코드 제어 파일입니다.  MSSCCPRJ 활용 합니다.소스 코드 제어 정보가 되지 않습니다 소스에\-.proj와.sln 파일의 경우와 마찬가지로 제어 SCC 파일이입니다.  
  
## 1.2 버전의 변경 내용  
 원본 컨트롤 소스 제어 플러그 인 API 버전 1.1 기반으로 하는 플러그 인에서 소스 제어에 대 한 정보 \(.proj\) 프로젝트 및 솔루션 \(.sln\) 파일에 저장 됩니다.  소스 제어 정보를 데이터베이스 위치를 Auxpath로 지정 됩니다 및 Projname로 데이터베이스 내에서 특정 위치를 지정 합니다.  Projname은 일반적으로 다음이 작업 중 하나를 후 유효 하지 않습니다 때문에이 동작은 지점, 포크, 또는 복사 작업 후 문제가 발생할 수 있습니다.  
  
 소스 제어 플러그 인 api 사용 하는 버전 1.1 IDE ~ SAK 파일이 추가 될 경우 플러그 인 MSSCCPRJ를 지원 합니다.SCC 메서드를 소스 제어 정보를 저장 합니다.  소스 제어 플러그 인 API 버전 1.2 MSSCCPRJ에 대 한 지원을 검색 하는 새로운 기능을 제공 합니다.SCC 파일을 사용 하지 않고는 ~ SAK 파일이 있습니다.  자세한 내용은 [제거 ~ SAK 파일](../../extensibility/internals/elimination-of-tilde-sak-files.md)를 참조하십시오.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)