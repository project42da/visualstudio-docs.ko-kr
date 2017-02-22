---
title: "프로젝트 디자이너, 컴파일 페이지(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ProjectPropertiesCompile"
helpviewer_keywords: 
  - "컴파일, Visual Basic 프로젝트"
  - "컴파일, 옵션[Visual Basic]"
  - "컴파일러, Visual Basic 옵션"
  - "컴파일, 명령[Visual Basic]"
  - "컴파일러 옵션, Visual Basic"
  - "프로젝트 디자이너, 컴파일 페이지"
  - "프로젝트 디자이너의 컴파일 페이지"
ms.assetid: b2a80230-906e-4e85-b3e0-fcd9c40426e1
caps.latest.revision: 60
caps.handback.revision: 60
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 프로젝트 디자이너, 컴파일 페이지(Visual Basic)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 디자이너의 **컴파일** 페이지를 사용하여 컴파일 지침을 지정할 수 있습니다.  고급 컴파일러 옵션 및 빌드 전\/빌드 후 이벤트도 이 페이지에서 지정할 수 있습니다.  
  
 액세스 하는  **컴파일** 페이지에서 프로젝트 노드를 선택 \(않습니다는  **솔루션** 노드\)에서  **솔루션 탐색기**.  다음 선택  **프로젝트**,  **속성** 메뉴 모음.  프로젝트 디자이너가 나타나면 **컴파일** 탭을 클릭합니다.  
  
 [!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## 구성 및 플랫폼  
 다음 설정을 사용하여 표시하거나 수정할 구성과 플랫폼을 선택할 수 있습니다.  
  
> [!NOTE]
>  단순화된 빌드 구성에서는 프로젝트 시스템에서 디버그 버전을 빌드할지 또는 릴리스 버전을 빌드할지 결정합니다.  따라서 **구성** 및 **플랫폼** 목록이 표시되지 않습니다.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
 **구성**  
 표시하거나 수정할 구성 설정을 지정합니다.  설정은 **디버그**\(기본값\), **릴리스** 또는 **모든 구성**입니다.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e) 및 [방법: 구성 만들기 및 편집](../../ide/how-to-create-and-edit-configurations.md)을 참조하십시오.  
  
 **플랫폼**  
 표시하거나 수정할 플랫폼 설정을 지정합니다.  사용자 지정할 수 있습니다  **Any CPU** \(기본값\)  **x 64**, 또는  **x86**.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
## 컴파일러 구성 옵션  
 다음 설정을 사용하여 컴파일러 구성 옵션을 설정할 수 있습니다.  
  
 **빌드 출력 경로**  
 프로젝트 구성에 사용할 출력 파일의 위치를 지정합니다.  이 상자에 빌드 출력 경로를 입력하거나, **찾아보기** 단추를 클릭하여 경로를 선택합니다.  이 경로는 상대적이므로 절대 경로를 입력하면 상대 경로로 저장됩니다.  기본 경로는 bin\\Debug\\ or bin\\Release\\입니다.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
 단순화된 빌드 구성에서는 프로젝트 시스템에서 디버그 버전을 빌드할지 또는 릴리스 버전을 빌드할지 결정합니다.  **디버그** 메뉴에서 **빌드** 명령을 클릭\(F5\)하면 지정한 **출력 경로**에 관계없이 디버그 위치에 빌드가 배치됩니다.  그러나 **빌드** 메뉴에서 **빌드** 명령을 클릭하면 사용자가 지정한 위치에 빌드가 배치됩니다.  자세한 내용은 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)을 참조하십시오.  
  
 **Option Explicit**  
 변수의 암시적 선언을 허용할지 여부를 지정합니다.  명시적 변수 선언을 수행하도록 하려면 **On**을 선택합니다.  따라서 변수를 선언하지 않고 사용할 경우 컴파일러에서 오류를 보고합니다.  변수의 암시적 선언을 허용하려면 **Off**를 선택합니다.  
  
 이 설정은 [\/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit) 컴파일러 옵션에 해당합니다.  
  
 소스 코드 파일에 [Option Explicit Statement](/dotnet/visual-basic/language-reference/statements/option-explicit-statement)이 포함된 경우 문에서 `On` 또는 `Off` 값은 **컴파일 페이지**에서 **Option Explicit** 설정을 재정의합니다.  
  
 새 프로젝트를 만들면 **컴파일 페이지**의 **Option Explicit** 설정이 **옵션** 대화 상자에서 **Option Explicit** 설정의 값으로 설정됩니다.  이 대화 상자에서 설정을 보거나 변경하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **VB 기본값**을 클릭합니다.  **VB 기본값**에서 **Option Explicit**의 최초 기본 설정은 **On**입니다.  
  
 일반적으로 **Option Explicit**을 `Off`로 설정하는 것은 좋지 않습니다.  하나 이상의 위치에서 변수 이름을 잘못 입력하면 프로그램이 실행될 때 예상하지 않은 결과가 나타날 수 있습니다.  
  
 **Option Strict**  
 엄격한 형식 의미 체계를 적용할지 여부를 지정합니다.  **Option Strict**가 **On**이면 다음 조건에서 컴파일 시간 오류가 발생합니다.  
  
-   암시적 축소 변환  
  
-   런타임에 바인딩  
  
-   `Object` 유형이 되는 암시적 입력  
  
 암시적 축소 변환 오류는 축소 변환인 암시적 데이터 형식 변환이 있을 경우 발생합니다.  자세한 내용은 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement), [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions) 및 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)을 참조하십시오.  
  
 개체가 `Object` 형식으로 선언된 변수의 속성 또는 메서드에 할당될 때 바인딩됩니다.  자세한 내용은 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement) 및 [Early and Late Binding](/dotnet/visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding)을 참조하십시오.  
  
 선언된 변수에 대해 적절한 형식을 유추할 수 없는 경우 암시적 개체 형식 오류가 발생하므로 `Object` 형식이 유추됩니다.  이는 주로 `Dim` 문을 통해 `As` 절을 사용하지 않고 변수를 선언할 때와 `Option Infer`가 해제되었을 경우 발생합니다.  자세한 내용은 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement), [Option Infer Statement](/dotnet/visual-basic/language-reference/statements/option-infer-statement) 및 [Visual Basic Language Specification](/dotnet/visual-basic/reference/language-specification)을 참조하십시오.  
  
 **Option Strict** 설정은 [\/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) 컴파일러 옵션에 해당합니다.  
  
 소스 코드 파일에 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)이 포함된 경우 문에서 `On` 또는 `Off` 값은 **컴파일 페이지**에서 **Option Strict** 설정을 재정의합니다.  
  
 프로젝트를 만들면 **컴파일 페이지**의 **Option Strict** 설정이 **옵션** 대화 상자의 **Option Strict** 설정 값으로 설정됩니다.  이 대화 상자에서 설정을 보거나 변경하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **VB 기본값**을 클릭합니다.  **VB 기본값**에서 **Option Strict**의 최초 기본 설정은 **Off**입니다.  
  
 **Option Strict 개별 경고입니다. 컴파일 페이지**의 **경고 구성** 섹션에는 `Option Strict`이 설정되어 있는 경우 컴파일 타임 오류를 유발하는 세 가지 조건에 해당하는 설정이 있습니다.  이러한 설정은 다음과 같습니다.  
  
-   **암시적 변환**  
  
-   **런타임에 바인딩; 런타임에 호출이 실패할 수 있습니다.**  
  
-   **암시적 형식; 개체로 간주**  
  
 **Option Strict**를 **설정**으로 설정하면 이 경고 구성 설정 중 3개 항목이 모두 **오류**로 설정됩니다.  **Option Strict**를 **Off**로 설정하면 모든 설정이 **None**으로 설정됩니다.  
  
 각 경고 구성 설정을 **없음**, **경고** 또는 **오류**로 개별적으로 변경할 수 있습니다.  세 가지 경고 구성 설정 모두 **오류**로 설정된 경우 `Option strict` 상자에 `On`이 나타납니다.  세 개 모두 **없음**으로 설정된 경우 이 상자에 `Off`가 나타납니다.  이러한 설정의 다른 조합에 대해서는 **\(사용자 지정\)**이 나타납니다.  
  
 **Option Compare**  
 사용할 문자열 비교의 형식을 지정합니다.  컴파일러에서 대\/소문자를 구분하는 이진 문자열 비교를 사용하도록 지시하려면 **Binary**를 선택합니다.  대\/소문자를 구분하지 않는 로캘 관련 텍스트 문자열 비교를 사용하려면 **Text**를 선택합니다.  
  
 이 설정은 [\/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare) 컴파일러 옵션에 해당합니다.  
  
 소스 코드 파일에 [Option Compare Statement](/dotnet/visual-basic/language-reference/statements/option-compare-statement)이 포함된 경우 문에서 `Binary` 또는 `Text` 값은 **컴파일 페이지**에서 **옵션 비교** 설정을 재정의합니다.  
  
 프로젝트를 만들면 **컴파일 페이지**의 **Option Compare** 설정이 **옵션** 대화 상자의 **Option Compare** 설정 값으로 설정됩니다.  이 대화 상자에서 설정을 보거나 변경하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **VB 기본값**을 클릭합니다.  **VB 기본값**에서 **Option Compare**의 최초 기본 설정은 **Binary**입니다.  
  
 **Option Infer**  
 변수 선언에 지역 형식 유추를 허용할지 여부를 지정합니다.  로컬 형식 유추의 사용을 허용하려면 **On**을 선택합니다.  지역 형식 유추를 차단하려면 **Off**를 선택하십시오.  
  
 이 설정은 [\/optioninfer](/dotnet/visual-basic/reference/command-line-compiler/optioninfer) 컴파일러 옵션에 해당합니다.  
  
 소스 코드 파일에 [Option Infer Statement](/dotnet/visual-basic/language-reference/statements/option-infer-statement)이 포함된 경우 문에서 `On` 또는 `Off` 값은 **컴파일 페이지**에서 **Option Infer** 설정을 재정의합니다.  
  
 프로젝트를 만들면 **컴파일 페이지**의 **Option Infer** 설정이 **옵션** 대화 상자의 **Option Infer** 설정 값으로 설정됩니다.  이 대화 상자에서 설정을 보거나 변경하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **VB 기본값**을 클릭합니다.  **VB 기본값**에서 **Option Infer**의 최초 기본 설정은 **On**입니다.  
  
 **대상 CPU**  
 출력 파일의 대상이 될 프로세서를 지정합니다.  지정  **x86** 모든 32 비트 Intel 호환 프로세서를  **x 64** 모든 64 비트 Intel 호환 프로세서를  **ARM** ARM 프로세서용 또는  **Any CPU** 모든 프로세서를 받아들일 수 있도록 지정 합니다.  **모든 CPU** 응용 프로그램을 실행할 하드웨어 종류의 최대를 허용 하기 때문에 새 프로젝트의 기본값입니다.  
  
 자세한 내용은 [\/platform](/dotnet/visual-basic/reference/command-line-compiler/platform)을 참조하십시오.  
  
 **32 비트를 선호 합니다.**  
 경우는  **Prefer32 비트** 확인란을 선택 하 고 모두 32 비트 및 64 비트 버전의 Windows에는 32 비트 응용 프로그램으로 응용 프로그램을 실행 합니다.  그렇지 않으면 응용 프로그램을 32 비트 응용 프로그램으로 32 비트 버전의 Windows와 64 비트 버전의 Windows에서 64 비트 응용 프로그램으로 실행 됩니다.  
  
 실행 포인터 크기, 64 비트 응용 프로그램을 두 배로 하 고 독점적으로 32 비트 라이브러리와의 호환성 문제를 일으킬 수 있습니다.  사용 하면 훨씬 빠르게 실행 또는 4GB 이상의 메모리를 요구만 하면 64 비트 응용 프로그램을 실행 하는 것이 있습니다.  
  
 이 확인란은만 다음 조건이 모두 참인 경우에 사용할 수 있습니다.  
  
-   에  **컴파일 페이지**,  **대상 CPU** 로 설정 된 목록  **Any CPU**.  
  
-   에  **응용 프로그램 페이지**,  **응용 프로그램 종류** 목록 지정 프로젝트는 응용 프로그램입니다.  
  
-   에  **응용 프로그램 페이지**,  **대상 프레임 워크** 목록은.NET Framework 4.5를 지정 합니다.  
  
 **경고 구성**  
 이 표에서는 빌드 조건과 해당하는 알림 수준\(**없음**, **경고** 또는 **오류**\)을 보여 줍니다.  
  
 기본적으로 컴파일하는 동안 모든 컴파일러 경고는 작업 목록에 추가됩니다.  컴파일러에서 경고나 오류를 발생시키지 않도록 하려면 **모든 경고 사용 안 함**을 선택합니다.  컴파일러에서 경고를 해결해야 하는 오류로 처리하도록 하려면 **모든 경고를 오류로 처리**를 선택합니다.  
  
 **모든 경고 사용 안 함**  
 컴파일러가 이 문서의 앞부분에 설명된 **조건 및 알림** 표에 지정된 대로 알림을 생성하도록 허용할지 여부를 지정합니다.  이 확인란은 기본적으로 선택되어 있지 않습니다.  컴파일러에서 경고나 오류를 발생시키지 않도록 하려면 이 확인란을 선택합니다.  
  
 이 설정은 [\/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) 컴파일러 옵션에 해당합니다.  
  
 **모든 경고를 오류로 처리**  
 경고 처리 방법을 지정합니다.  기본적으로 이 확인란은 선택되어 있지 않으므로 모든 경고 알림이 **경고**로 설정된 상태를 유지합니다.  모든 경고 알림을 **오류**로 변경하려면 이 확인란을 선택합니다.  
  
 **모든 경고 사용 안 함**이 선택되지 않은 경우에만 이 옵션을 사용할 수 있습니다.  
  
 **XML 문서 파일 생성**  
 문서 정보를 생성할지 여부를 지정합니다.  기본적으로 이 확인란은 선택되어 있으며, 컴파일러에서 문서 정보를 생성하여 XML 파일에 포함하도록 합니다.  컴파일러에서 문서를 만들지 않도록 하려면 이 확인란의 선택을 취소합니다.  
  
 이 설정은 [\/doc](/dotnet/visual-basic/reference/command-line-compiler/doc) 컴파일러 옵션에 해당합니다.  
  
 **COM Interop 등록**  
 COM 개체가 응용 프로그램과 상호 작용할 수 있도록, 관리되는 응용 프로그램에서 COM 개체\(COM 호출 가능 래퍼\)를 노출하도록 할 것인지를 지정합니다.  
  
 기본적으로 이 확인란은 선택되어 있지 않으며, 응용 프로그램이 COM Interop를 허용하지 않도록 지정합니다.  COM Interop를 허용하려면 이 확인란을 선택합니다.  
  
 Windows 응용 프로그램 또는 콘솔 응용 프로그램 프로젝트에는 이 옵션을 사용할 수 없습니다.  
  
 **빌드 이벤트**  
 이 단추를 클릭하여 **빌드 이벤트** 대화 상자에 액세스합니다.  이 대화 상자를 사용하면 프로젝트에 대한 빌드 전 및 빌드 후 구성 지침을 지정할 수 있습니다.  이 대화 상자는 Visual Basic 프로젝트에만 적용됩니다.  자세한 내용은 [빌드 이벤트 대화 상자\(Visual Basic\)](../../ide/reference/build-events-dialog-box-visual-basic.md)을 참조하십시오.  
  
 **고급 컴파일 옵션**  
 이 단추를 클릭하여 **고급 컴파일러 설정** 대화 상자에 액세스합니다.  **고급 컴파일러 설정** 대화 상자를 사용하면 프로젝트의 고급 빌드 구성 속성을 지정할 수 있습니다.  이 대화 상자는 Visual Basic 프로젝트에만 적용됩니다.  자세한 내용은 [고급 컴파일러 설정 대화 상자\(Visual Basic\)](../../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md)을 참조하십시오.  
  
## 참고 항목  
 [Debug and Release Project Configurations](http://msdn.microsoft.com/ko-kr/0440b300-0614-4511-901a-105b771b236e)   
 [Managing Compilation Properties](http://msdn.microsoft.com/ko-kr/94308881-f10f-4caf-a729-f1028e596a2c)   
 [방법: 빌드 이벤트 지정\(Visual Basic\)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Visual Basic Command\-Line Compiler](/dotnet/visual-basic/reference/command-line-compiler/index)   
 [방법: 구성 만들기 및 편집](../../ide/how-to-create-and-edit-configurations.md)