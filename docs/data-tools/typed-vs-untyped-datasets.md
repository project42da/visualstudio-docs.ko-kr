---
title: 형식화 되지 않은 데이터 집합과 비교 입력
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: c83ba0bb-5425-4d47-8891-6b4dbf937701
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: e5819a208a54a5a4235330216e46b5e17f1260fa
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="typed-vs-untyped-datasets"></a>형식화 되지 않은 데이터 집합과 비교 입력
형식화 된 데이터 집합은 먼저 기본에서 파생 되는 데이터 집합 <xref:System.Data.DataSet> 클래스 하 고 다음 정보를 사용 하 여는 **데이터 집합 디자이너**, dataset 클래스를 강력한 형식의 새로운를 생성 하는.xsd 파일에 저장 되어 있습니다. 스키마 (테이블, 열 및 등)에서 정보 생성 이며 첫 번째 클래스 개체 및 속성의 집합으로이 새 데이터 집합 클래스도 컴파일됩니다. 형식화 된 데이터 집합 기본에서 상속 하기 때문에 <xref:System.Data.DataSet> 의 기능을 모두 클래스, 형식화 된 가정은 <xref:System.Data.DataSet> 클래스 및 인스턴스를 사용 하는 메서드와 함께 사용할 수는 <xref:System.Data.DataSet> 클래스를 매개 변수로 합니다.

 반면, 형식화 되지 않은 데이터 집합을 해당 기본 제공 스키마를에 있습니다. 형식화 된 데이터 집합에서와 같이 형식화 되지 않은 데이터 집합을 사용 하 여 테이블, 열 및 등을 포함-있지만 컬렉션 으로만 표시 되는 것입니다. 그러나 (수동으로 만든 후 테이블 및 다른 데이터 요소에는 형식화 되지 않은 데이터 집합을 내보낼 수 있습니다 데이터 집합의 구조에 스키마로 데이터 집합의를 사용 하 여 <xref:System.Data.DataSet.WriteXmlSchema%2A> 메서드.)

## <a name="contrasting-data-access-in-typed-and-untyped-datasets"></a>대비 되는 형식화 및 형식화 되지 않은 데이터 집합의 데이터 액세스
 형식화 된 데이터 집합에 대 한 클래스는 테이블 및 열의 실제 이름에 해당 속성 걸릴 개체 모델을 있습니다. 예를 들어 형식화 된 데이터 집합을 사용 하는 경우 다음과 같은 코드를 사용 하 여 열을 참조할 수 있습니다.

 [!code-csharp[VbRaddataDatasets#4](../data-tools/codesnippet/CSharp/typed-vs-untyped-datasets_1.cs)]
 [!code-vb[VbRaddataDatasets#4](../data-tools/codesnippet/VisualBasic/typed-vs-untyped-datasets_1.vb)]

 반대로 형식화 되지 않은 데이터 집합을 사용 하는 경우 해당 하는 코드는:

 [!code-csharp[VbRaddataDatasets#5](../data-tools/codesnippet/CSharp/typed-vs-untyped-datasets_2.cs)]
 [!code-vb[VbRaddataDatasets#5](../data-tools/codesnippet/VisualBasic/typed-vs-untyped-datasets_2.vb)]

 형식화 된 액세스는만 쉽게 읽을 수 있지만 intellisense에서 완벽 하 게 지원는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **코드 편집기**합니다. 형식화 된 데이터 집합에 대 한 구문을 더 쉽게 작업할 수 있을 뿐 형식 컴파일 타임에 검사 데이터 집합 멤버에 값을 할당할 때 오류가 발생할 가능성이 크게 감소를 제공 합니다. 에 있는 열의 이름을 변경 하면 프로그램 <xref:System.Data.DataSet> 클래스 및 다음 응용 프로그램을 컴파일, 빌드 오류가 표시 됩니다. 빌드 오류를 두 번 클릭 하 고 **작업 목록**, 이전 열 이름을 참조 하는 코드의 줄에 직접 이동할 수 있습니다. 형식화 된 테이블 및 열에 대 한 액세스 되지 런타임 컬렉션을 통해 컴파일 타임에 결정 됩니다 때문에 데이터 집합이 런타임 시 약간 더 빠르며 이기도 합니다.

 형식화 된 데이터 집합을 확보 하더라도 경우의 장점은 형식화 되지 않은 데이터 집합을 사용 하 여 다양 한 상황에에서 유용 합니다. 가장 확실 한 시나리오는 스키마가 없는 데이터 집합에 사용할 수 있는 경우입니다. 이 발생할 수 있으며, 예를 들어 응용 프로그램은 데이터 집합을 반환 하는 구성 요소와 상호 작용 하는 경우 하지만 모르는 미리의 구조를 합니다. 마찬가지로, 정적, 예측 가능한 구조 없는 데이터로 작업할 때 경우가 있습니다. 이 경우 것 불가능 형식화 된 데이터 집합을 사용 하도록 데이터 구조에서 각 변경 형식화 된 dataset 클래스를 다시 생성 해야 하기 때문에 있습니다.

 보다 일반적으로, 있습니다 여러 번 사용할 수 있는 스키마 필요 없이 동적으로 데이터 집합을 만들 수 있습니다. 이 경우 데이터 집합은 단순히 편리한 구조를 정보를 유지할 수 있습니다으로 데이터를 관계형으로 나타낼 수 있습니다. 이와 동시에 XML 파일로 쓰지 또는 다른 프로세스에 전달 하는 정보를 serialize 하는 기능 등의 데이터 집합의 기능을 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

- [데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)