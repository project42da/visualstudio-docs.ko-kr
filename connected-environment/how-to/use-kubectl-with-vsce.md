---
title: 연결된 환경을 통해 kubectl를 사용하는 방법 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 03/12/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: Azure에서 마이크로 서비스 및 컨테이너를 사용하여 신속하게 Kubernetes 개발
keywords: Docker, Kubernetes, Azure, AKS, Azure Container Service, 컨테이너
manager: douge
ms.openlocfilehash: 138dce09e0d53dc47703b9c6f56a7efda4adc255
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="use-kubectl-with-a-connected-environment"></a>연결된 환경을 통해 `kubectl`을 사용

연결된 환경 내에서 Kubernetes 클러스터에 액세스하고 `kubectl`과 같은 기존 Kubernetes 도구를 사용할 수 있습니다.

`vsce env create` 또는 `vsce env select`의 실행은 사용자에 대해 `kubectl` 구성 컨텍스트를 자동으로 추가하게 되므로 kubectl은 VSCE Kubernetes 클러스터에 이미 연결되어 있어야 합니다. 예를 들면 다음과 같습니다.
- 현재 컨텍스트를 확인합니다: `kubectl config current-context`
- 사용 가능한 모든 라이브러리를 나열합니다: `kubectl config get-contexts`. VSCE에서 만든 kubernetes 클러스터는 "vsce-<guid>"과 같은 이름으로 불리게 됩니다.
- 컨텍스트 변경: `kubectl config use-context <context-name>`
- Kubernetes 대시보드 보기: `kubectl proxy`을 실행한 다음, 이 명령이 내보내는 주소에서 브라우저를 엽니다(Kubernetes 대시보드로 이동하려면 URL에 `/ui`를 추가합니다).
- *주*라고 하는 기본 VSCE 공간에서 실행 중인 서비스를 나열: `kubectl get services --namespace=mainline`

