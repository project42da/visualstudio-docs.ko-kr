---
title: '&lt;customErrorReporting&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <customErrorReporting> element [ClickOnce deployment manifest]
ms.assetid: 7d31816e-c692-46b5-9cc9-753284b3bcda
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 44094a76472679598c42f7a38ef44838502a51ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ltcustomerrorreportinggt-element-clickonce-deployment"></a>&lt;customErrorReporting&gt; 요소 (ClickOnce 배포)
오류가 발생할 때 표시할 URI를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<customErrorReporting  
   uri  
/>  
```  
  
## <a name="remarks"></a>설명  
 이 요소는 선택적입니다. 없으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 예외 스택 보여 주는 오류 대화 상자를 표시 합니다. 경우는 `customErrorReporting` 요소가 있는지 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 변수에 지정 된 URI를 대신 표시는 `uri` 매개 변수입니다. 대상 URI 매개 변수로 외부 예외 클래스, 내부 예외 클래스 및 내부 예외 메시지가 포함 됩니다.  
  
 이 요소를 사용 하 여 응용 프로그램에 오류 보고 기능을 추가 합니다. 생성 된 URI의 오류 유형에 대 한 정보를 포함 하므로 웹 사이트 및 표시 되는 적절 한 문제 해결 화면 예를 들어 구문 분석할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 조각에서 `customErrorReporting` 요소를 함께 생성 된 URI 생성할 수 있습니다.  
  
```  
<customErrorReporting uri=http://www.contoso.com/applications/error.asp />  
  
Example Generated Error:  
http://www.contoso.com/applications/error.asp? outer=System.Deployment.Application.InvalidDeploymentException&&inner=System.Deployment.Application.InvalidDeploymentException&&msg=The%20application%20manifest%20is%20signed,%20but%20the%20deployment%20manifest%20is%20unsigned.%20Both%20manifests%20must%20be%20either%20signed%20or%20unsigned.  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)