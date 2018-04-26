---
title: 데이터 집합을 XML로 저장 합니다.
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 07c0b4b508acf90aac6e65e0a5f4a426bd2fce50
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="save-a-dataset-as-xml"></a>데이터 집합을 XML로 저장 합니다.

데이터 집합에서 사용할 수 있는 XML 메서드를 호출 하 여 데이터 집합의 XML 데이터를 액세스할 수 있습니다. XML 형식으로 데이터를 저장 하려면 호출 하면는 <xref:System.Data.DataSet.GetXml%2A> 메서드 또는 <xref:System.Data.DataSet.WriteXml%2A> 의 메서드는 <xref:System.Data.DataSet>합니다.

호출 된 <xref:System.Data.DataSet.GetXml%2A> 메서드는 XML로 서식이 지정 된 데이터 집합의 모든 데이터 테이블에서 데이터를 포함 하는 문자열을 반환 합니다.

호출 된 <xref:System.Data.DataSet.WriteXml%2A> 메서드는 사용자가 지정한 파일에 XML 형식의 데이터를 보냅니다.

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>변수에 데이터 집합에 XML로 데이터를 저장 하려면

- <xref:System.Data.DataSet.GetXml%2A> 메서드가 반환 되는 <xref:System.String>합니다. 형식의 변수 선언 <xref:System.String> 의 결과 지정 하 고는 <xref:System.Data.DataSet.GetXml%2A> 메서드.

     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-csharp[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>파일에 XML로 데이터 집합에 데이터를 저장 하려면

- <xref:System.Data.DataSet.WriteXml%2A> 메서드에 여러 오버 로드가 있습니다. 변수를 선언 하 고 파일을 저장할 올바른 경로 할당 합니다. 다음 코드를 파일에 데이터를 저장 하는 방법을 보여 줍니다.

     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-csharp[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]

## <a name="see-also"></a>참고자료

- [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)