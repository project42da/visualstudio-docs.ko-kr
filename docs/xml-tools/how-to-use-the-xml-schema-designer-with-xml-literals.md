---
title: '방법: XML 리터럴과 함께 XML 스키마 디자이너 사용'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 589bfa54a0ba1a7efb2964cf5b74446ca9ffe10d
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>방법: XML 리터럴과 함께 XML 스키마 디자이너를 사용 합니다.

이 항목에서는 Visual Basic 프로젝트에서 XML 리터럴과 연결된 스키마를 보는 방법에 대해 설명합니다.

## <a name="to-create-a-new-visual-basic-console-application-project"></a>새 Visual Basic 콘솔 응용 프로그램 프로젝트를 만들려면

1.  Visual Studio를 시작합니다.

2.  **파일** 메뉴 선택 **새로**를 선택한 후 **프로젝트**합니다. **새 프로젝트** 대화 상자가 나타납니다. 에 대 한 **프로젝트 형식**선택, **다른 언어** 선택한 후 **Visual Basic**합니다. 에 대 한 **템플릿**, 콘솔 응용 프로그램을 선택 합니다. 다음 입력 `XMLLiterals` 에 **이름** 필드와에서 프로젝트 위치는 **위치** 필드입니다. **확인**을 클릭합니다.

     새 프로젝트가 만들어집니다. XMLLiterals 프로젝트에 하나의 Visual Basic 소스 파일 *Module1.vb*합니다.

## <a name="to-add-an-existing-xsd-file-to-the-project"></a>기존 XSD 파일을 프로젝트에 추가하려면

1.  새 텍스트 파일을 메모장에서 엽니다. XML 스키마 샘플 코드를 복사 [구매 주문 스키마](../xml-tools/sample-xsd-file-simple-schema.md) 파일에 붙여 넣습니다.

2.  파일 이름으로 일부 위치에 저장 *PurchaseOrderSchema.xsd*합니다.

3.  솔루션 탐색기에서 프로젝트의 이름을 마우스 오른쪽 단추로 클릭, 선택 **추가**를 선택한 후 **기존 항목**합니다. **AddExisting 항목** 대화 상자가 나타납니다. 찾아는 *PurchaseOrderSchema.xsd* 파일을 선택한 다음 클릭 **추가**합니다.

     XMLLiterals 프로젝트에는 이제 두 개의 파일 포함: *Module1.vb* 및 *PurchaseOrderSchema.xsd*합니다.

## <a name="to-add-visual-basic-code-with-an-xml-literal-based-on-the-xsd-file-included-in-the-project"></a>프로젝트에 포함된 XSD 파일을 기반으로 XML 리터럴이 있는 Visual Basic 코드를 추가하려면

1.  코드 *Module1.vb* 를 다음 코드로 파일:

   ```vb
   Imports <xmlns:ns="http://tempuri.org/PurchaseOrderSchema.xsd">

   Module Module1
       Sub Main()

           Dim XMLLiteral = <ns:PurchaseOrder OrderDate="1900-01-01">
                                <ns:ShipTo country="US">
                                    <ns:name>name1</ns:name>
                                    <ns:street>street1</ns:street>
                                    <ns:city>city1</ns:city>
                                    <ns:state>state1</ns:state>
                                    <ns:zip>1</ns:zip>
                                </ns:ShipTo>
                                <ns:BillTo country="US">
                                    <ns:name>name1</ns:name>
                                    <ns:street>street1</ns:street>
                                    <ns:city>city1</ns:city>
                                    <ns:state>state1</ns:state>
                                    <ns:zip>1</ns:zip>
                                </ns:BillTo>
                            </ns:PurchaseOrder>

       End Sub
   End Module
   ```

2.  XML 리터럴 또는 XML 네임 스페이스 가져오기에서 XML 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **스키마 탐색기에 표시**합니다.

     **XML 스키마 탐색기** XML 스키마 집합과 연결 된 XML 리터럴이 있는 Visual Basic 파일과 나란히 표시 됩니다.