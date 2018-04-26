---
title: .NET 용 visual Studio data tools
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3175080-1dfb-4ab8-a460-92dadbb844b4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
- dotnet
ms.openlocfilehash: d2db4210085e3dc16d9c4b9e00653312ae0d5a82
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="visual-studio-data-tools-for-net"></a>.NET 용 visual Studio data tools

Visual Studio 및.NET Framework에는 광범위 한 API와 도구를 데이터베이스에 연결, 데이터를 메모리에 모델링 및 데이터의 사용자 인터페이스에 표시에 대 한 지원 제공 함께 합니다. 데이터 액세스 기능을 제공 하는.NET Framework 클래스 라고 [ADO.NET](/dotnet/framework/data/adonet/index)합니다. Visual Studio에서 도구는 데이터와 함께 ADO.NET 관계형 데이터베이스 및 XML을 지원 하기 위해 주로 원래 설계 되었습니다. 많은 NoSQL 데이터베이스 공급 업체 또는 제 3 자가 이러한 일 전 부터는 ADO.NET 공급자에 제공합니다.

[.NET core](/dotnet/core/) ADO.NET 데이터 집합 및 관련 된 형식을 제외 하 고 지원 합니다. .NET Core 대상으로 하는 개체-관계형 매핑 (ORM) 계층을 필요로 하는 경우 사용 하 여 [Entity Framework Core](/ef/core/)합니다.

다음 다이어그램에서는 기본 아키텍처의 대략적인된 개요를 보여 줍니다.

![ADO.NET 아키텍처](../data-tools/media/raddata-ado-net-architecture-diagram.png)

일반적인 과정은 다음과 같습니다.

1. 개발 또는 테스트 데이터베이스를 로컬 컴퓨터에 설치 합니다. 참조 [데이터베이스 시스템, 도구 및 샘플을 설치](../data-tools/installing-database-systems-tools-and-samples.md)합니다. Azure 데이터 서비스를 사용 하는 경우에이 단계가 필요 하지 않습니다.

2. Visual Studio에서 데이터베이스 (또는 서비스 또는 로컬 파일)에 대 한 연결을 테스트 합니다. 참조 [새 연결 추가](../data-tools/add-new-connections.md)합니다.

3. (선택 사항) 도구를 사용 하 여 생성 하 고 새 모델을 구성 합니다. Entity Framework를 기반으로 모델은 새 응용 프로그램에 대 한 기본 권장 사항을 합니다. 모델 중 하나를 사용 하는 응용 프로그램 상호 작용 하는 데이터 원본입니다. 모델은 데이터베이스 또는 서비스와 응용 프로그램 사이 논리적으로 있습니다. 참조 [새 데이터 원본을 추가](../data-tools/add-new-data-sources.md)합니다.

4. 데이터 소스를 끌어는 **데이터 소스** 창으로 Windows Forms, ASP.NET 또는 Windows Presentation Foundation 디자인 화면을 지정 하는 방식으로 사용자에 게 데이터를 표시 하 여 데이터 바인딩 코드를 생성 합니다. 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.

5. 비즈니스 규칙, 검색 및 데이터 유효성 검사와 같은 또는 기본 데이터베이스를 노출 하는 사용자 지정 기능을 활용 하는 항목에 대 한 사용자 지정 코드를 추가 합니다.

3 단계를 건너뛰고 모델을 사용 하지 않고 데이터베이스에 직접 명령 실행 하는.NET 응용 프로그램을 프로그래밍할 수 있습니다. 이 경우에 관련 설명서를 찾을 수 있습니다: [ADO.NET](/dotnet/framework/data/adonet/index)합니다. Note 여전히 사용할 수 있는 데이터 소스 구성 마법사 및 디자이너에 메모리와 해당 개체에 데이터 바인딩 UI 컨트롤에 사용자 정의 개체를 채울 때 데이터 바인딩 코드를 생성 합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)