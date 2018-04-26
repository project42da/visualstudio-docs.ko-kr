---
title: TableAdapter의 기능을 확장
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9b5884ff140097010c90fbf2208fecd95980f2fe
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>TableAdapter의 기능을 확장
TableAdapter의 partial 클래스 파일에 코드를 추가 하 여 TableAdapter의 기능을 확장할 수 있습니다.

 TableAdapter를 정의 하는 코드에서 TableAdapter 변경 될 때 다시 생성 됩니다는 **데이터 집합 디자이너**, 마법사는 TableAdapter의 구성을 수정 하는 경우 또는 합니다. 코드를 TableAdapter의 재생성 하는 동안 삭제 되지 않도록 방지 하려면 TableAdapter의 partial 클래스 파일에 코드를 추가 합니다.

 Partial 클래스는 여러 개의 물리적 파일에서 나눌 수 특정 클래스에 대 한 코드를 사용 합니다. 자세한 내용은 참조 [부분](/dotnet/visual-basic/language-reference/modifiers/partial) 또는 [부분 (형식)](/dotnet/csharp/language-reference/keywords/partial-type)합니다.

## <a name="locate-tableadapters-in-code"></a>코드에서 Tableadapter를 찾기
 Tableadapter로 설계 되어는 **데이터 집합 디자이너**, 생성 된 TableAdapter 클래스가 아닌 중첩된 클래스의 <xref:System.Data.DataSet>합니다. Tableadapter는 TableAdapter의 연결 된 데이터 집합의 이름을 기반으로 하는 네임 스페이스에 있습니다. 예를 들어, 응용 프로그램 이라는 데이터 집합이 있으면 `HRDataSet`, Tableadapter에 있을 것은 `HRDataSetTableAdapters` 네임 스페이스입니다. (명명 규칙은이 패턴을 따릅니다: *DatasetName* + `TableAdapters`).

 다음 예에서는 가정 라는 TableAdapter `CustomersTableAdapter`사용 하 여 프로젝트에 `NorthwindDataSet`합니다.

#### <a name="to-create-a-partial-class-for-a-tableadapter"></a>TableAdapter에 대 한 partial 클래스를 만들려면

1.  새 클래스를 이동 하 여 프로젝트에 추가 **프로젝트** 메뉴에서 **클래스 추가**합니다.

2.  클래스 이름을 `CustomersTableAdapterExtended`로 지정합니다.

3.  선택 **추가**합니다.

4.  올바른 네임 스페이스 및 프로젝트에 대 한 partial 클래스 이름을 가진 코드를 다음과 같이 바꿉니다.

     [!code-csharp[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]

## <a name="see-also"></a>참고자료

- [TableAdapter를 사용하여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)