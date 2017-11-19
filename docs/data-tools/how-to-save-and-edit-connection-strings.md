---
title: "방법: 저장 하 고 연결 문자열 편집 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ef3a2c-029c-423b-9d9e-a4f1add4f640
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 4a7482c269cd978d2c1848c896985b1194797e42
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-save-and-edit-connection-strings"></a>방법: 연결 문자열 저장 및 편집
Visual Studio 응용 프로그램의 연결 문자열 (응용 프로그램 설정 라고도 함) 응용 프로그램 구성 파일에 저장 하거나 응용 프로그램에 직접 하드 코드 될 수 있습니다. 응용 프로그램 구성 파일에 연결 문자열을 저장하면 응용 프로그램 유지 관리 작업을 간소화할 수 있습니다. 연결 문자열을 변경해야 하는 경우 소스 코드에서 문자열을 변경한 다음 응용 프로그램을 다시 컴파일하는 대신 응용 프로그램 설정 파일에서 문자열을 업데이트할 수 있습니다.

암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 응용 프로그램 구성 파일에 저장된 연결 문자열은 암호화되거나 난독 처리되지 않으므로 다른 사람이 파일에 액세스하여 해당 내용을 볼 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 Windows 통합 보안을 사용하는 방법이 더 안전합니다.

Windows 통합 보안을 사용하도록 선택하지 않았는데 데이터베이스에 사용자 이름과 암호가 필요한 경우 연결 문자열에서 사용자 이름과 암호를 생략할 수 있습니다. 그러나 데이터베이스에 정상적으로 연결하려면 응용 프로그램이 이 정보를 제공해야 합니다. 예를 들어 이 정보를 입력하라는 메시지를 사용자에게 표시하고 런타임에 연결 문자열을 동적으로 작성하는 대화 상자를 만들 수 있습니다. 데이터베이스로 전송되는 와중에 정보를 가로챌 수 있는 경우에도 보안 문제가 발생할 수 있습니다. 자세한 내용은 [연결 정보 보호](/dotnet/framework/data/adonet/protecting-connection-information)를 참조하세요.

## <a name="to-save-a-connection-string-from-within-the-data-source-configuration-wizard"></a>데이터 소스 구성 마법사 내에서 연결 문자열을 저장 하려면
에 **데이터 소스 구성 마법사**는 연결 문자열 저장 응용 프로그램 구성 파일 페이지에서 연결을 저장 하도록 선택 합니다.

## <a name="to-save-a-connection-string-directly-into-application-settings"></a>연결 문자열을 응용 프로그램 설정에 직접 저장하려면
- 솔루션 탐색기에서 내 프로젝트 아이콘 (Visual Basic) 또는 (C#) 프로젝트 디자이너를 열려면 속성 아이콘을 두 번 클릭 합니다.
- 설정 탭을 선택 합니다.
- 연결 문자열에 대 한 이름을 입력 합니다. 코드에서 연결 문자열에 액세스할 때 이 이름을 참조합니다.
- (연결 문자열)의 유형을 설정 합니다.
- 응용 프로그램으로 설정 하는 범위를 그대로 둡니다.
- 값 필드에 연결 문자열을 입력 하거나 연결 문자열을 작성할 연결 속성 대화 상자를 열려면 값 필드에서 줄임표 (...) 단추를 클릭 합니다.  

## <a name="editing-connection-strings-stored-in-application-settings"></a>응용 프로그램 설정에 저장 된 연결 문자열 편집
프로젝트 디자이너를 사용 하 여 응용 프로그램 설정에 저장 된 연결 정보를 수정할 수 있습니다.  

### <a name="to-edit-a-connection-string-stored-in-application-settings"></a>응용 프로그램 설정에 저장된 연결 문자열을 편집하려면
- 솔루션 탐색기에서 내 프로젝트 아이콘 (Visual Basic) 또는 (C#) 프로젝트 디자이너를 열려면 속성 아이콘을 두 번 클릭 합니다.
- 설정 탭을 선택 합니다.
- 편집 하 고 값 필드에 텍스트를 선택 하려는 연결을 찾습니다.
- 값 필드에 연결 문자열을 편집 하거나 연결 속성 대화 상자를 사용 하 여 연결을 편집 하려면 값 필드에서 줄임표 (...) 단추를 클릭 합니다.  

## <a name="editing-connection-strings-for-datasets"></a>데이터 집합에 대 한 연결 문자열 편집
데이터 집합의 각 TableAdapter에 대 한 연결 정보를 수정할 수 있습니다.  

### <a name="to-edit-a-connection-string-for-a-tableadapter-in-a-dataset"></a>데이터 집합에서 TableAdapter에 대 한 연결 문자열을 편집 하려면
- 솔루션 탐색기에서 데이터 집합 (.xsd 파일)를 편집 하려면 연결 된 두 번 클릭 합니다.
- TableAdapter 또는 편집 하려면 연결 된 쿼리를 선택 합니다.
- 속성 창에서 연결 노드를 확장 합니다.
- 연결 문자열을 신속 하 게 수정 하는 경우 연결 문자열 속성을 편집 또는 연결 속성에서 아래쪽 화살표를 클릭 하 고 새 연결을 선택 합니다.

## <a name="security"></a>보안
암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 Windows 통합 보안을 사용하는 방법이 더 안전합니다.
자세한 내용은 [연결 정보 보호](/dotnet/framework/data/adonet/protecting-connection-information)를 참조하세요.
  
## <a name="see-also"></a>참고 항목
[연결 추가](../data-tools/add-new-connections.md)