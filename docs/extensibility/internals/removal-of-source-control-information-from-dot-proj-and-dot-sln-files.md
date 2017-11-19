---
title: "소스 제어 정보를 제거 합니다. Proj 및 합니다. Sln 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73ea933a7e9efc08347ea107b089101f1e5d5459
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>소스 제어 정보를 제거 합니다. Proj 및 합니다. Sln 파일
SCC는 소스 제어 플러그 인 API의 버전 1.2의에서 정보는 MSSCCPRJ에 저장 됩니다. SCC 파일입니다. MSSCCPRJ 활용 합니다. SCC 파일을 SCC 정보는 원본이 아닌-.proj 및.sln 파일 만큼 제어입니다.  
  
## <a name="version-12-changes"></a>버전 1.2 변경 내용  
 소스 제어 플러그 인에서 소스 제어 플러그 인 API 버전 1.1 기반으로 하는, 소스 제어에 대 한 정보 (.proj) 프로젝트 및 솔루션 (.sln) 파일에 저장 됩니다. 소스 제어 정보가 데이터베이스 위치는 AuxPath로 지정 됩니다 되며 데이터베이스 내의 특정 위치 ProjName 지정 됩니다. 이 문제는 ProjName는 일반적으로 유효 하지 후 다음이 연산 중 하나 때문에 지점, 분기 또는 복사 작업 후 문제가 발생할 수 있습니다.  
  
 소스 제어 플러그 인 API 사용 되는 버전 1.1에서는 IDE에서에서 ~ SAK 파일이 추가 플러그 인 지원는 MSSCCPRJ 경우. 소스 제어 정보를 저장할 경우의 SCC 메서드입니다. 소스 제어 플러그 인 API 버전 1.2 MSSCCPRJ 지원 되는 검색에 대 한 새 기능을 제공 합니다. SCC 파일을 사용 하지 않고는 ~ SAK 파일입니다. 자세한 내용은 참조 [의 제거로 인해 ~ SAK 파일](../../extensibility/internals/elimination-of-tilde-sak-files.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)