---
title: "SCVMM 2008 R2를 SCVMM 2012로 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Upgrade SCVMM 2008 R2 to SCVMM 2012, test lab
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 51d907dfe25d8f27065b2a4d8bbecaa3e98e42a1
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="upgrade-scvmm-2008-r2-to-scvmm-2012"></a>SCVMM 2008 R2를 SCVMM 2012로 업그레이드

Team Foundation Server용 Lab Management는 SCVMM 2008 R2 및 SCVMM 2012를 지원합니다. Team Foundation Server 2013을 Team Foundation Server 2015로 업그레이드 중이며 SCVMM 2008 R2를 SCVMM 2012로 업그레이드하려는 경우 Team Foundation Server 2015로 업그레이드를 완료한 후 SCVMM 2012로 업그레이드하는 것이 좋습니다. 이 항목에서는 Team Foundation Server 2015에서 Lab Management를 사용할 때 SCVMM 2008 R2를 SCVMM 2012로 업그레이드하는 방법을 설명합니다.
Lab Management는 SCVMM 2016을 지원하지 **않습니다**. 

**중요:** SCVMM을 업그레이드할 때 특정 단계를 수행하면 Team Foundation Server에서 가동 중지 시간이 발생합니다. 아래에서 관련 단계를 찾을 수 있습니다.

## <a name="upgrading-to-scvmm-2012"></a>SCVMM 2012로 업그레이드

1. SCVMM 2012 설치 관리자를 사용하여 SCVMM 2008 R2 서버를 SCVMM 2012 서버로 업그레이드합니다.

1. 호스트 및 라이브러리 공유의 SCVMM 에이전트를 업그레이드합니다.

1. SCVMM 관리 콘솔을 사용하여 SCVMM 구성 요소가 모두 작동하는지 확인합니다.

1. Team Foundation Server의 모든 응용 프로그램 계층 컴퓨터에 SCVMM 2012 관리 콘솔을 설치합니다.

1. **iisreset** 명령을 사용하여 Team Foundation Server 웹 서비스를 다시 시작합니다. 그런 다음 Team Foundation Server 작업 에이전트를 다시 시작합니다.

   **주의:** 이 단계는 Team Foundation Server의 서비스를 방해합니다.

1. SCVMM과 호환되도록 각 프로젝트 컬렉션 데이터베이스의 데이터 및 템플릿을 업그레이드합니다. 
   2012.

   Team Foundation Server에서 관리자 권한 명령 프롬프트를 열고 다음 명령을 입력합니다.

   **C:\\Program Files\\Microsoft Team Foundation Server 14.0\\Tools\> tfsconfig lab /upgradeSCVMM /collectionName:\***

   **upgradeSCVMM** 명령을 사용하는 경우 Team Foundation Server는 해당 템플릿을 사용하는 모든 팀 프로젝트에 대해 SCVMM 서버에 새 템플릿 개체를 만듭니다. 이렇게 하면 데이터 손실 없이 템플릿이 SCVMM 2012와 호환되도록 업그레이드됩니다. 그러나 새 템플릿을 만들면 팀 프로젝트 이름이 템플릿 이름에 추가됩니다.

   **주의:**  
   새 템플릿 이름이 64자보다 긴 경우 SCVMM 오류가 발생합니다. 이 오류를 해결하려면 해당 템플릿에 더 짧은 이름을 지정해야 합니다. 이 명령을 실행할 때 다른 오류 또는 경고가 발생하는 경우 다음 섹션을 참조하여 해당 오류를 해결하세요. 오류 또는 경고가 발생하지 않으면 업그레이드가 완료되고 Lab Management와 함께 SCVMM 환경을 사용할 수 있습니다.

## <a name="resolving-errors-and-warnings-when-using-the-upgradescvmm-command"></a>UpgradeSCVMM 명령을 사용할 때 오류 및 경고 해결

**upgradeSCVMM** 명령을 사용한 후 Lab Management를 사용하기 전에 표시되는 모든 오류 또는 경고를 해결한 다음, 명령을 다시 실행해야 합니다. **upgradeSCVMM** 명령은 발생하는 오류 및 경고에 대한 정보가 포함된 로그 파일을 생성합니다. **upgradeSCVMM** 명령을 실행하면 로그 파일의 위치가 표시됩니다.

**SCVMM 실패:** SCVMM 실패와 관련된 오류가 표시되는 경우 SCVMM 작업 기록을 사용하여 오류에 대한 추가 정보를 가져옵니다. SCVMM에서 오류를 해결한 후 **upgradeSCVMM** 명령을 다시 실행합니다.

## <a name="see-also"></a>참고 항목

* [기존 Lab Management 구성 변경](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx)
