---
title: VBA 만들거나 Microsoft Office System 프로젝트에 대 한 Visual Studio Tools 열에 대 한 액세스를 사용 하도록 설정
decsprition: You must explicitly enable access to the Office VBA project system before you can create or open a Visual Studio Tools for Office System project
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vst.project.vbawrongversion
- VST.Project.VBASecurityGenericError
- VST.Project.VBASecurityPermissions
- VST.SelectDocWizard.MissingCOM
- VST.Project.VBASecurityNotSet
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 05c7296412ffd3f87433f4790617f4b27ca75ae3
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="enable-access-to-vba-to-create-or-open-a-visual-studio-tools-for-the-microsoft-office-system-project"></a>VBA 만들거나 Microsoft Office System 프로젝트에 대 한 Visual Studio Tools 열에 대 한 액세스를 사용 하도록 설정

전에 작성 하거나 Microsoft Office System 프로젝트에 대 한 Visual Studio Tools를 열 수 있습니다에 명시적으로 Microsoft office에서 VBA 프로젝트 시스템에 대 한 Visual Basic에 대 한 액세스를 사용 해야 합니다.

 Microsoft Office 개발 프로젝트의 프로젝트 응용 프로그램에 대 한 Visual Basic을 사용 하지 않으므로 경우에 Microsoft Office Word 및 Microsoft Office Excel의 VBA 프로젝트 시스템에 대 한 Visual Basic에 대 한 액세스를 해야 합니다. Visual Basic 및 C# 프로젝트의 디자인 타임 컨트롤 지원은 Visual Basic for Applications 프로젝트 시스템에 따라 달라집니다.

 일부 Microsoft Office 매크로 바이러스는 자신을 전파하기 위한 수단으로 Visual Basic for Applications 프로젝트 시스템을 자동화하려 할 수 있습니다. Visual Basic for Applications 프로젝트 시스템에 액세스할 수 있도록 설정하는 순간 매크로 바이러스 확산을 방지할 수 있는 안전 기능이 작동하지 않게 되는 것입니다. 그러나 일반적인 매크로 보안은 계속 적용되므로 Office 응용 프로그램에 대해 유지 관리하는 신뢰할 수 있는 게시자 목록과 매크로 보안 수준을 통해 매크로를 컴퓨터에서 실행해도 되는지 여부가 결정됩니다.

> [!NOTE]
> 이 옵션은 개발 컴퓨터에만 적용됩니다. 최종 사용자 컴퓨터에 Office 솔루션을 실행할 수 있도록 설정 하는이 옵션이 필요 하지 않습니다.

 Visual Basic for Applications 프로젝트 시스템에 액세스할 수 없도록 설정하는 것 자체만으로는 바이러스로부터 컴퓨터를 보호할 수 없으며, 컴퓨터가 매크로 바이러스에 감염되는 경우 일부 바이러스가 다른 문서로 확산되는 것을 중지할 수 있을 뿐입니다. 이 옵션은 컴퓨터에 대한 추가 보호 계층으로 기본적으로 사용하지 않도록 설정됩니다. 그러나 이 옵션을 사용하도록 설정해도 보안 모범 사례를 따르면 컴퓨터가 바이러스에 더 감염되기 쉬운 상태가 되지는 않습니다.

 최상의 방지 Office 매크로 바이러스 Office를 높음 또는 매우 높음 보안 수준의 매크로만 신뢰를 실행 하려면 확인 된 알려진된 출처 고 보안 패치 및 바이러스 스캐너를 최신 상태로 유지 합니다.

 바이러스와 기타 악성 코드 로부터 PC를 보호 하는 방법에 대 한 자세한 내용은 참조 [ http://www.microsoft.com/protect ](http://www.microsoft.com/protect)합니다.

 옵션을 해제 하거나 설정할 수 있습니다 **Visual Basic 프로젝트에 안전 하 게 액세스할** 수동으로 합니다.

 VBA 또는 COM 오류가 발생하는 경우에는 Office 설치를 복구할 수 있습니다.

## <a name="to-enable-or-disable-access-to-visual-basic-projects"></a>Visual Basic 프로젝트에 액세스하거나 할 수 없도록 설정하려면

1. **파일** 탭을 클릭합니다.

2. **옵션**을 클릭합니다.

3. 클릭 **보안 센터**, 클릭 하 고 **보안 센터 설정**합니다.

4. 에 **보안 센터**, 클릭 **매크로 설정**합니다.

5. 선택 하거나 선택 취소할 **VBA 프로젝트의 개체 모델에 대 한 액세스를 신뢰** 활성화 하거나 Visual Basic 프로젝트에 대 한 액세스를 비활성화 하 합니다.

6. **확인**을 클릭합니다.

### <a name="to-enable-or-disable-access-to-visual-basic-projects-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office system와 Visual Basic 프로젝트에 대 한 액세스를 사용 하지 않도록 설정 하거나 설정 하려면

1. 에 **도구** 메뉴 Word 또는 Excel에서 가리키고 **매크로**, 클릭 하 고 **보안**합니다.

2. 에 **보안** 대화 상자를 클릭는 **신뢰할 수 있는 게시자** 탭 합니다.

3. 을 사용 하려면 또는 사용 하지 않도록 설정, 해제 하려면 선택을 선택 **Visual Basic 프로젝트에 안전 하 게 액세스할**합니다.

4. **확인**을 클릭합니다.

## <a name="to-set-your-office-macro-security-level"></a>Office 매크로 보안 수준을 설정하려면

1. **파일** 탭을 클릭합니다.

2. **옵션**을 클릭합니다.

3. 클릭 **보안 센터**, 클릭 하 고 **보안 센터 설정**합니다.

4. 에 **보안 센터**, 클릭 **매크로 설정**합니다.

5. 에 **매크로 설정** 섹션에서 원하는 설정을 선택 합니다.

6. **확인**을 클릭합니다.

### <a name="to-set-your-office-macro-security-level-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office system와 Office 매크로 보안 수준을 설정 하려면

1. 에 **도구** 메뉴 Word 또는 Excel에서 가리키고 **매크로**, 클릭 하 고 **보안**합니다.

2. 에 **보안 수준을** 탭에서 원하는 설정을 선택 합니다.

    **보안 수준을** 탭 각 수준에 대 한 세부 정보를 포함 합니다. 자세한 내용은 Office 도움말에서 "매크로 보안 수준" 항목을 참조하세요.

### <a name="to-install-vba-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office system과 함께 VBA를 설치하려면

1. 제어판에서 실행 **프로그램 추가 / 제거** 또는 **프로그램 및 기능**합니다.

2. 사무실에서 선택 된 **현재 설치 된 프로그램** 목록입니다.

3. **변경**을 클릭합니다.

4. 선택 **기능 추가 / 제거**, 클릭 하 고 **계속**합니다.

5. 선택 **고급 응용 프로그램의 사용자 지정 선택**, 클릭 하 고 **다음**합니다.

6. 확장 **Office 공유 기능** 에 **응용 프로그램 및 도구에 대 한 업데이트 옵션을 선택** 목록입니다.

7. 옆의 드롭다운 메뉴를 열고 **응용 프로그램에 대 한 Visual Basic**, 클릭 하 고 **내 컴퓨터에서 실행**합니다.

8. **계속**을 클릭합니다.

9. **닫기**를 클릭합니다.

## <a name="to-repair-your-installation-of-office"></a>Office 설치를 복구하려면

1. 제어판에서 실행 **프로그램 추가 / 제거** 또는 **프로그램 및 기능**합니다.

2. 에 Office 버전을 선택는 **현재 설치 된 프로그램** 목록입니다.

3. **변경**을 클릭합니다.

4. 선택 **다시 설치 또는 복구**, 클릭 하 고 **다음**합니다.

5. 선택 **Office 설치에서 오류를 검색 및 복구**, 클릭 하 고 **설치**합니다.

## <a name="see-also"></a>참고자료

 [Office 솔루션 보안](../vsto/securing-office-solutions.md)