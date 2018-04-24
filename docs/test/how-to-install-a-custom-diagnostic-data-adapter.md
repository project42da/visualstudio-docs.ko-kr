---
title: '방법: Visual Studio에서 사용자 지정 진단 데이터 어댑터 설치 | Microsoft Docs'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, installing
ms.assetid: 907e65d8-0408-44b3-9e5e-e631892c1726
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 9154760fff3305343d06e63150c49db06c720ef6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-install-a-custom-diagnostic-data-adapter"></a>방법: 사용자 지정 진단 데이터 어댑터 설치

사용자 지정 진단 데이터 어댑터를 만든 경우 또는 사용할 사용자 지정 진단 데이터 어댑터가 제공된 경우 진단 데이터 어댑터에 대한 어셈블리 파일을 로컬 컴퓨터의 올바른 디렉터리에 복사하여 진단 데이터 어댑터 어셈블리를 설치할 수 있습니다.

 환경에서 역할에 대한 사용자 지정 진단 데이터 어댑터를 사용할 경우 이 역할에 사용할 수 있는 테스트 에이전트를 실행하는 모든 컴퓨터에 진단 데이터 어댑터를 설치할 수 있습니다.

 다음 절차에 따라 사용자 지정 진단 데이터 어댑터를 적합한 위치에 설치합니다. 진단 데이터 어댑터를 설치할 컴퓨터에 대한 관리자 권한이 있어야 합니다.

## <a name="installing-a-custom-diagnostic-data-adapter"></a>사용자 지정 진단 데이터 어댑터 설치

### <a name="to-install-a-custom-diagnostic-data-adapter"></a>사용자 지정 진단 데이터 어댑터를 설치하려면

1.  클라이언트 컴퓨터 또는 에이전트 컴퓨터에 대한 테스트를 실행할 때 진단 데이터 어댑터를 사용하려면 설치 경로를 기준으로 사용자 빌드 디렉터리의 모든 파일을 대상 컴퓨터의 다음 디렉터리에 복사합니다.

     *%Program Files(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*

     복사할 파일:

    -   진단 데이터 어댑터 어셈블리(.dll)(필수)

    -   어댑터에 대한 디버그 데이터 파일(.pdb)(선택 사항)

    -   어댑터에 대한 구성 파일(`<diagnostic data adapter name>.dll.config`)(기본 구성 설정을 사용하는 경우)(선택 사항)

    -   구성 편집기 어셈블리(어댑터의 구성 설정을 편집하기 위해 만든 경우)(선택 사항). 클라이언트 컴퓨터에만 해당됩니다. 에이전트 컴퓨터에서는 편집기를 사용하지 않습니다.

    > [!NOTE]
    > 진단 데이터 어댑터와 구성 편집기는 동일한 프로젝트에서 만들어서 동일한 어셈블리에서 기본 제공할 수 있지만, 필요한 경우 개별 프로젝트를 사용하여 개별 어셈블리를 만들 수 있습니다.

     테스트를 실행할 때 환경을 사용하도록 테스트 설정을 구성하는 방법에 대한 자세한 내용은 [수동 테스트에서 진단 데이터 수집(VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)을 참조하세요.

2.  테스트에 대한 진단 데이터 어댑터를 선택하려면 먼저 기존 테스트 설정을 선택하거나 Microsoft Test Manager 또는 Visual Studio에서 새 항목을 만든 후 선택한 테스트 설정의 **데이터 및 진단** 탭에서 진단 데이터 어댑터를 선택해야 합니다.

3.  진단 데이터 어댑터 구성 편집기를 만들어 설치한 경우 테스트 설정에 대한 진단 데이터 어댑터를 구성하려면 해당 어댑터 옆의 **구성**을 선택하고 변경 작업을 수행합니다. 그런 다음, **저장**을 선택합니다. 진단 데이터 수집기의 구성 편집기를 만드는 방법에 대한 자세한 내용은 [방법: 진단 데이터 어댑터의 데이터에 대한 사용자 지정 편집기 만들기](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)를 참조하세요.

4.  Microsoft Test Manager에서 테스트를 실행할 경우 테스트를 실행하기 전에 테스트 계획에 이러한 테스트 설정을 할당하거나 **옵션과 함께 실행** 명령을 사용하여 테스트 설정을 할당하고 테스트 설정을 재정의할 수 있습니다. 테스트 설정에 대한 자세한 내용은 [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)을 참조하세요.

     Visual Studio에서 테스트를 실행하는 경우 이러한 테스트 설정을 활성으로 설정해야 합니다. 테스트 설정에 대한 자세한 내용은 [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)을 참조하세요.

5.  진단 데이터 어댑터가 선택된 테스트 설정을 사용하여 테스트를 실행합니다.

## <a name="see-also"></a>참고 항목

- [방법: 진단 데이터 어댑터 만들기](../test/how-to-create-a-diagnostic-data-adapter.md)
- [방법: 진단 데이터 어댑터 데이터용 사용자 지정 편집기 만들기](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [진단 데이터 어댑터를 만들기 위한 샘플 프로젝트](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)
- [진단 데이터 어댑터를 만들어 사용자 지정 데이터를 수집하거나 테스트 컴퓨터에 영향 주기](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)