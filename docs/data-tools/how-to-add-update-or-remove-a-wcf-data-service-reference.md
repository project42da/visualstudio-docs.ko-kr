---
title: '방법: WCF 데이터 서비스 참조 추가, 업데이트 또는 제거'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- service references [Visual Studio]
- WCF Data Service reference
- WCF data service references
- ADO.NET service references
- ADO.NET Data Service reference
ms.assetid: 892ebf37-3af4-472e-8744-92837677d611
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4dba04455c4ac6ea6d124911b836d24ab2ec63ec
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-add-update-or-remove-a-wcf-data-service-reference"></a>방법: WCF 데이터 서비스 참조 추가, 업데이트 또는 제거
A *서비스 참조* 하면 하나 이상의 액세스 하려면 프로젝트 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]합니다. 사용 하 여는 **서비스 참조 추가** 대화 상자를 검색할 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 인터넷 또는 로컬 영역 네트워크에서 로컬에서 현재 솔루션의 합니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="adding-a-service-reference"></a>서비스 참조 추가

#### <a name="to-add-a-reference-to-an-external-service"></a>외부 서비스에 대 한 참조를 추가 하려면

1.  **솔루션 탐색기**, 서비스를 추가 하 고 클릭 하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 **서비스 참조 추가**합니다.

     **서비스 참조 추가** 대화 상자가 나타납니다.

2.  에 **주소** 상자, 서비스에 대 한 URL을 입력 한 다음 클릭 **이동** 는 서비스를 검색 합니다. 서비스 사용자 이름 및 암호 보안을 구현 하는 경우 사용자 이름 및 암호에 대 한 라는 메시지가 표시 될 수 있습니다.

    > [!NOTE]
    >  신뢰할 수 있는 원본의 서비스만 참조해야 합니다. 신뢰할 수 없는 원본에서 참조를 추가하면 보안이 손상될 수 있습니다.

     URL을 선택할 수도 있습니다는 **주소** 유효한 서비스 메타 데이터가 발견 된 이전 15 Url을 저장 하는 목록입니다.

     검색은 수행 하는 경우 진행률 표시줄이 표시 됩니다. 클릭 하 여 언제 든 지 검색을 중지할 수 **중지**합니다.

3.  에 **서비스** 목록에서 엔터티 집합을 선택 하려는 서비스에 대 한 노드를 확장 합니다.

4.  에 **Namespace** 상자, 참조에 사용 하려는 네임 스페이스를 입력 합니다.

5.  클릭 **확인** 프로젝트에 참조를 추가 합니다.

     서비스 클라이언트 (프록시)가 생성 되 고 서비스를 설명 하는 메타 데이터는 app.config 파일에 추가 됩니다.

#### <a name="to-add-a-reference-to-a-service-in-the-current-solution"></a>현재 솔루션에에서는 서비스에 대 한 참조를 추가 하려면

1.  **솔루션 탐색기**, 서비스를 추가 하 고 클릭 하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 **서비스 참조 추가**합니다.

     **서비스 참조 추가** 대화 상자가 나타납니다.

2.  클릭 **검색**합니다.

     모든 서비스 (둘 다 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 및 WCF 서비스) 현재 솔루션에 추가 되 고 **서비스** 목록입니다.

3.  에 **서비스** 목록에서 엔터티 집합을 선택 하려는 서비스에 대 한 노드를 확장 합니다.

4.  에 **Namespace** 상자, 참조에 사용 하려는 네임 스페이스를 입력 합니다.

5.  클릭 **확인** 프로젝트에 참조를 추가 합니다.

     서비스 클라이언트 (프록시)가 생성 되 고 서비스를 설명 하는 메타 데이터는 app.config 파일에 추가 됩니다.

## <a name="updating-a-service-reference"></a>서비스 참조 업데이트
 엔터티 데이터 모델에 대 한는 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] 변경 되기도 합니다. 이 경우 서비스 참조 업데이트 되어야 합니다.

#### <a name="to-update-a-service-reference"></a>서비스 참조를 업데이트 하려면

-   **솔루션 탐색기**, 서비스 참조를 마우스 오른쪽 단추로 클릭 하 고 클릭 **서비스 참조 업데이트**합니다.

     참조가 원래 위치에서 업데이트 되 고 메타 데이터에 변경 내용을 반영 하는 서비스 클라이언트 생성 하는 동안 진행률 대화 상자가 표시 됩니다.

## <a name="removing-a-service-reference"></a>서비스 참조를 제거합니다.
 서비스 참조를 더 이상 사용 중인 경우 솔루션에서 제거할 수 없습니다.

#### <a name="to-remove-a-service-reference"></a>서비스 참조를 제거 하려면

-   **솔루션 탐색기**, 서비스 참조를 마우스 오른쪽 단추로 클릭 하 고 클릭 **삭제**합니다.

     서비스 클라이언트에서 솔루션을 제거한 app.config 파일에서 서비스를 설명 하는 메타 데이터를 제거 됩니다.

    > [!NOTE]
    >  서비스 참조를 참조 하는 코드를 수동으로 제거 해야 합니다.

## <a name="see-also"></a>참고자료

- [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)