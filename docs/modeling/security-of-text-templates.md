---
title: "텍스트 템플릿 보안 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, security
ms.assetid: 567a2383-7d43-4acc-af4a-cd70b7a0151e
caps.latest.revision: "23"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 7c99f0a519ec62a2b9946baba072b0256a78697a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="security-of-text-templates"></a>텍스트 템플릿 보안
텍스트 템플릿은 다음과 같은 보안 문제가 있습니다.  
  
-   텍스트 템플릿은 임의의 코드가 삽입에 취약 합니다.  
  
-   지시문 프로세서를 찾는 데 사용 하는 호스트 하는 메커니즘이 안전 하지 않은 경우에 악의적인 지시문 프로세서를 실행할 수 있습니다.  
  
## <a name="arbitrary-code"></a>임의의 코드  
 서식 파일을 작성할 때 내의 모든 코드를 넣을 수 있습니다는 \<# # > 태그가 있습니다. 따라서 임의의 코드를 텍스트 템플릿 내에서 실행할 수 있습니다.  
  
 신뢰할 수 있는 원본에서 서식 파일을 가져올 해야 합니다. 신뢰할 수 있는 출처에서 제공 하지 않는 템플릿을 실행 하지 않도록 응용 프로그램의 최종 사용자에 게 경고 해야 합니다.  
  
## <a name="malicious-directive-processor"></a>악의적인 지시문 프로세서  
 텍스트 템플릿 엔진 변환 호스트 및 하나 이상의 지시문 프로세서를 변환 출력 파일에 템플릿 텍스트와 상호 작용 합니다. 자세한 내용은 참조 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)합니다.  
  
 지시문 프로세서를 찾는 데 사용 하는 호스트 하는 메커니즘 안전 하지 않으면 악의적인 지시문 프로세서 실행의 위험을 실행 됩니다. 악의적인 지시문 프로세서에서 실행 되는 코드를 제공할 수 `FullTrust` 모드는 템플릿이 실행 될 때입니다. 사용자 지정 텍스트 템플릿 변환 호스트를 만드는 경우 지시문 프로세서를 찾도록 엔진에 대 한 레지스트리와 같은 보안 메커니즘을 사용 해야 합니다.