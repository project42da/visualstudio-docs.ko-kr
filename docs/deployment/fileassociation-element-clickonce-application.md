---
title: '&lt;fileAssociation&gt; 요소 (ClickOnce 응용 프로그램) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <fileAssociation> element [ClickOnce application manifest]
- manifests [ClickOnce], fileAssociation element
ms.assetid: 8f951b4f-54f9-412e-a9e5-af4e379fcf08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1f59ef1d00951d4c49c1bcb19c6c9122e281c3ca
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ltfileassociationgt-element-clickonce-application"></a>&lt;fileAssociation&gt; 요소 (ClickOnce 응용 프로그램)
응용 프로그램에 연결할 파일 확장명을 식별 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<fileAssociation  
    xmlns="urn:schemas-microsoft-com:clickonce.v1"  
    extension  
    description  
    progid  
    defaultIcon  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `fileAssociation` 요소는 선택적입니다. 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`extension`|필수. 응용 프로그램에 연결할 파일 확장명입니다.|  
|`description`|필수. 셸에서 사용 하기 위해 파일 형식을 설명 합니다.|  
|`progid`|필수. 파일 형식을 고유 하 게 식별 하는 이름입니다.|  
|`defaultIcon`|필수. 이 확장을 사용 하 여 파일에 대해 사용할 아이콘을 지정 합니다. 아이콘 파일을 사용 하 여 지정 해야 합니다는 [ \<파일 > 요소](../deployment/file-element-clickonce-application.md) 내에서 [ \<어셈블리 > 요소](../deployment/assembly-element-clickonce-application.md) 이 요소를 포함 하 합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소에 대 한 XML 네임 스페이스 참조를 포함 해야 합니다 ":-microsoft-com:clickonce.v1"입니다. 경우는 `<fileAssociation>` 요소는 사용, 뒤에 야는 `<application>` 부모에서 요소 [ \<어셈블리 > 요소](../deployment/assembly-element-clickonce-application.md)합니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기존 파일 연결을 덮어쓰지 않습니다. 그러나 ClickOnce 응용 프로그램은 현재 사용자에 대 한 파일 확장명을 재정의할 수 있습니다. ClickOnce 응용 프로그램을 제거한 후 ClickOnce 사용자에 대 한 파일 연결을 삭제 하 고 컴퓨터 연결이 다시 활성입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `fileAssociation` 응용 프로그램의 요소를 사용 하 여 배포 하는 텍스트 편집기 응용 프로그램에 대 한 매니페스트 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]합니다. 이 코드 예제도 포함 되어는 [ \<파일 > 요소](../deployment/file-element-clickonce-application.md) 에 필요한는 `defaultIcon` 특성입니다.  
  
```  
<file name="text.ico" size="4286">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>0joAqhmfeBb93ZneZv/oTMP2brY=</dsig:DigestValue>  
  </hash>  
</file>  
<file name="writing.ico" size="9662">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>2cL2U7cm13nG40v9MQdxYKazIwI=</dsig:DigestValue>  
  </hash>  
</file>  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".text" description="Text  Document (ClickOnce)" progid="Text.Document" defaultIcon="text.ico" />  
<fileAssociation xmlns="urn:schemas-microsoft-com:clickonce.v1" extension=".writing" description="Writings (ClickOnce)" progid="Writing.Document" defaultIcon="writing.ico" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)