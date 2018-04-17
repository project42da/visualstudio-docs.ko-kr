---
title: 도메인 클래스의 속성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain class
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 419315e5d8ec44f8065b704612bc50c1788974e3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-domain-classes"></a>도메인 클래스의 속성
도메인 클래스는 다음 표에 속성이 있습니다. 도메인 클래스에 대 한 정보를 참조 하십시오. [이해 모델, 클래스 및 관계](../modeling/understanding-models-classes-and-relationships.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|액세스 한정자|도메인 클래스의 액세스 수준입니다(`public` 또는 `internal`).|`public`|  
|사용자 지정 특성|이 도메인 클래스에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<없음 >|  
|Double 생성 파생|경우 `True`, 기본 클래스 및 (재정의 통해 사용자 지정은 지원) 하는 partial 클래스를 모두 생성 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|`False`|  
|사용자 지정 생성자|경우 `True`, 사용자 지정 생성자의 소스 코드에서 제공 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|`False`|  
|상속 한정자|도메인 클래스에서 생성 되는 소스 코드 클래스의 상속의 종류를 설명 (`none`, `abstract` 또는 `sealed`).|`none`|  
|기본 클래스|이 도메인 클래스 파생 되는 경우 기본 클래스의 이름입니다.|\<없음 >|  
|이름|이 도메인 클래스의 이름입니다.|현재 이름|  
|네임스페이스|이 도메인 클래스의 네임 스페이스입니다.|현재 네임 스페이스|  
|노트|이 도메인 클래스와 연관 된 비공식 메모 합니다.|\<없음 >|  
|설명|생성 된 디자이너의 UI를 문서화 하는 데 사용 되는 설명입니다.|\<없음 >|  
|표시 이름|이 도메인 클래스에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<없음 >|  
|Help Keyword|이 도메인 클래스에 대 한 F1 도움말을 인덱싱하는 데 사용할 optional 키워드|\<없음 >|  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)