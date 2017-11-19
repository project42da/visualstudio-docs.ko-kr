---
title: "격리 된 셸 응용 프로그램 서비스에 대 한 지침이 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio Shell integrated mode, serviceability
- Shell integrated mode [Visual Studio], serviceability
ms.assetid: 747d1a47-b8b3-4e8b-93c0-768724be48f2
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5f99631db1709a17aaf9809669bbeb2f69b10e2a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="servicing-guidelines-for-isolated-shell-applications"></a>격리 셸 응용 프로그램에 대 한 지침을 서비스
Visual Studio 격리 셸 응용 프로그램을 배포할 때 설치 된 후 응용 프로그램에 대 한 소프트웨어 업데이트를 제공할 수 있어야 합니다. 이 위해 Microsoft Installer (MSI) 파일을 사용 하 여 응용 프로그램을 설치 해야 합니다. 이러한 종류의 설치 웹이 재배포할 수에 Microsoft에서 제공 하는 소프트웨어 업데이트 다운로드 하 여 사용자 지정 작업 없이도 고객에서 사용할 수 있습니다.  
  
## <a name="servicing-requirements"></a>서비스 요구 사항을  
 격리 셸 설치 설치 프로그램에는 다음 세 가지 조건을 충족 하는지 확인 하 여 업데이트를 허용할 수 있는지 확인할 수 있습니다.  
  
### <a name="redistribute-by-using-an-msi"></a>MSI를 사용 하 여 재배포  
 응용 프로그램을 재배포 하는 MSI를 사용 해야, 응용 프로그램 MSI 제품 관련 정보를 유지 하며 그 있기 때문에 클라이언트 컴퓨터의 실제 위치를 포함 합니다. 병합 모듈 (.msm 파일) 이러한 보증을 제공 하지 않으면 및 사용할 수 없습니다.  
  
### <a name="accounting-for-custom-actions"></a>사용자 지정 작업에 대 한 계정  
 사용자 지정 작업은 설치 프로그램의 비표준 설치 지시문입니다. 사용자 지정 동작 파일 위치, 레지스트리 설정, 사용자 설정 또는 기타 설치 항목 등의 매개 변수를 변경합니다. 사용자 지정 작업 설치 시간에 데이터를 조작 될 수 있습니다.  
  
 설치 프로그램에서 사용자 지정 동작을 사용 하는 경우 모든 설치 시 사용자 지정 작업을 사용자 응용 프로그램을 제거 하는 경우 작업을 취소 하려면 해당 사용자 지정 작업 있어야 함을 확인 해야 합니다. 설치 프로그램 오류가 발생 하 여 해당 제공 사용자 지정 작업을 제거 하는 경우 응용 프로그램 제거도 상태로 유지 됩니다 부분적으로 설치 합니다.  
  
-   파일 또는 해시 값의 특정 버전을 사용 하는 사용자 지정 작업을 소프트웨어 업데이트 이러한 버전을 변경 하거나 값을 해시 하는 경우 실패 합니다. 이 경우 사용자 지정 작업 이러한 값을 수동으로 업데이트 해야 합니다. 또 다른 문제는 버전의 파일이 나 해시 값 제품 버전 간에 공유 되 면 발생 합니다. 가능 하면 이러한 종속성을 방지 합니다.  
  
### <a name="accounting-for-shared-files"></a>공유 파일에 대 한 계정  
 공유 파일 이름이 같은 및 여러 제품으로 같은 위치에 설치 됩니다. 이러한 제품 버전, 주식 유지 단위 (SKU) 또는 둘 다에서 달라질 수 있습니다 및 제품은 해당된 컴퓨터에 공존할 수 있습니다. 그러나 공유 파일 여러 가지 이유로 서비스 문제를 만듭니다.  
  
-   공유 파일을 업데이트 한 응용 프로그램에 대 한 업데이트는 업데이트 되지 않은 두 번째 응용 프로그램에서 사용 하는 파일의 버전 변경 될 수 있으므로 응용 프로그램 호환성 문제가 발생할 수 있습니다. 설치 관리자 파일을 공유 하는 제품에 대 한 공유 파일에 대 한 참조를 계산 합니다. 따라서는 제품을 제거 해도 파일 설치 된 인스턴스의 수 감소 외의 공유 파일 적용 되지 않습니다.  
  
-   엔지니어링 QFE (Quick Fix) 설치 관리자 QFE 설치 관리자 서비스를 제공 하는 제품의 버전에는 파일의 버전으로 되돌립니다. 이 프로세스는 잠재적으로 업데이트 된 파일 공유 배달에 응용 프로그램을 중단 합니다.