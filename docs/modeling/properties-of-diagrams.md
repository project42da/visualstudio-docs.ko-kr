---
title: 다이어그램의 속성
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language, diagram
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: bd02bd7f91d80392553d4c9f5e7ff10ab71b1abe
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="properties-of-diagrams"></a>다이어그램의 속성
생성 된 디자이너에서 다이어그램 모양을 지정 하는 속성을 설정할 수 있습니다. 예를 들어 다이어그램에 텍스트에 대 한 기본 색을 지정할 수 있습니다.

 자세한 내용은 참조 [도메인 특정 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.

 다음 표에서 다이어그램의 속성을 나열 합니다.

|속성|설명|기본|
|--------------|-----------------|-------------|
|채우기 색|다이어그램에 대 한 채우기 색입니다.|하얀|
|텍스트 색|다이어그램에 표시 되는 텍스트의 색입니다.|검정|
|액세스 한정자|클래스 (공용 또는 내부)의 액세스 한정자입니다.|Public|
|사용자 지정 특성|생성 된 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<없음 >|
|Double 생성 파생|경우 `True`, 기본 클래스 및 (재정의 통해 사용자 지정은 지원) 하는 partial 클래스를 모두 생성 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|
|사용자 지정 생성자|경우 `True`, 사용자 지정 생성자의 소스 코드에서 제공 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)...|False|
|상속 한정자|다이어그램에서 생성 되는 소스 코드 클래스의 상속의 종류를 설명 (`none`, `abstract` 또는 `sealed`).|없음|
|기본 다이어그램|이 다이어그램의 기본 클래스입니다.|(없음)|
|이름|이 다이어그램의 이름입니다.|현재 이름|
|네임스페이스|이 다이어그램와 연결 되어 있는 네임 스페이스입니다.|현재 네임 스페이스|
|클래스 표시|이 다이어그램을 나타내는 루트 도메인 클래스입니다.|해당 하는 경우 현재 루트 클래스|
|노트|이 요소와 연결 된 비공식 정보입니다.|\<없음 >|
|속성으로 노출 채우기 색|경우 `True`, 생성 된 디자이너의 다이어그램의 채우기 색을 설정할 수 있습니다. 이 설정 하려면 다이어그램 셰이프를 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가 Explosed**합니다.|False|
|텍스트 색 속성으로 노출|경우 `True`, 사용자 생성 된 디자이너에서 다이어그램의 텍스트 색을 설정할 수 있습니다. 이 설정 하려면 다이어그램 셰이프를 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가 Explosed**합니다.|False|
|설명|생성 된 디자이너를 문서화 하는 데 사용 되는 설명입니다.|\<없음 >|
|표시 이름|이 다이어그램에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<없음 >|
|Help Keyword|이 다이어그램에 대 한 F1 도움말을 인덱싱하는 데 사용 되는 키워드입니다.|\<없음 >|

## <a name="see-also"></a>참고 항목

- [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)