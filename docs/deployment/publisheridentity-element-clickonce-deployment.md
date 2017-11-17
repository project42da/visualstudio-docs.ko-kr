---
title: "&lt;publisherIdentity&gt; 요소 (ClickOnce 배포) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 9a59b97b3260beaf39ae20b62a44903add13e622
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt; 요소 (ClickOnce 배포)
이 배포 매니페스트에 서명한 게시자에 대한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `publisherIdentity` 요소는 서명 된 매니페스트에 필요 합니다. 다음 표에서 특성이 표시 하는 `publisherIdentity` 요소를 지원 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 요소. 이 응용 프로그램을 게시 하는 파티의 id에 설명 합니다.|  
|`issuerKeyHash`|필수 요소. 인증서 발급자의 공개 키의 sha-1 해시를 포함합니다.|  
  
#### <a name="parameters"></a>매개 변수  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
  
## <a name="subhead"></a>부제목