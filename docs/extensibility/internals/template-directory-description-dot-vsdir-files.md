---
title: "서식 파일 디렉터리 설명 (합니다. Vsdir) 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".vsdir 파일"
  - "VSDIR 파일"
  - "서식 파일 디렉터리 설명 파일"
ms.assetid: 9df51800-190e-4662-b685-fdaafcff1400
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 서식 파일 디렉터리 설명 (합니다. Vsdir) 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

서식 파일 디렉터리 설명 파일 (.vsdir)은 통합된 개발 환경 (IDE) 폴더, 마법사.vsz 파일 및 대화 상자에서 프로젝트와 연결 된 템플릿 파일을 표시할 수 있도록 하는 텍스트 파일. 내용이 파일 또는 폴더 마다 하나의 레코드를 포함합니다. 하나의.vsdir 파일 여러 개 폴더, 마법사 또는 템플릿 파일을 설명 하기 위해 일반적으로 제공 되는 참조 된 위치에서 모든.vsdir 파일 병합 됩니다.  
  
 .Vsdir 파일과.vsdir 파일 자체에서 참조 되는 파일 폴더 (하위 디렉터리)는 모두 동일한 디렉터리에 있습니다. IDE는 마법사를 실행 하 하거나 폴더 또는 파일에서 표시 하는 경우는 **새 프로젝트** 또는 **새 항목 추가** 대화 상자, IDE.vsdir 파일 있는지 여부를 결정 하는 실행된 파일을 포함 하는 디렉터리를 검사 합니다. .Vsdir 파일이 발견 되는 경우 실행 또는 표시 폴더 또는 파일에 대 한 항목이 포함 되어 있는지 확인 하는 IDE 읽습니다. 항목이 발견 되는 경우 마법사의 실행 또는 콘텐츠 표시에 정보를 사용 하는 IDE입니다.  
  
 다음 코드 예제는 SourceFiles.vsdir 파일에서에 \< EnvSDK>\BscPrj\BscPrj\BscPrjProjectItems\Source_Files 레지스트리 키:  
  
```  
HeaderFile.h|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#125|130|#126|0|0|0|#127  
SourceFile.cpp|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#122|110|#123|0|0|0|#124  
```  
  
 이 경우 두 레코드가 하나의 파일에 있습니다. 새 줄 (캐리지 리턴 문자)는 각 레코드를 구분합니다. 각 줄은 다른 파일 형식을 나타냅니다. 파이프 (&#124;) 문자는 각 레코드의 필드를 구분 합니다. 단일 디렉터리에 있는 다른 파일 이름을 가진 여러.vsdir 파일을 포함 하거나 각 파일 형식에 대 한 하나의.vsdir 파일이 할 수 있습니다.  
  
## <a name="fields"></a>필드  
 다음 표에서 각 레코드에 대해 지정 된 필드를 나열 합니다.  
  
|필드|설명|  
|-----------|-----------------|  
|상대 경로 이름 (RelPathName)|예: HeaderFile.h 또는 MyWizard.vsz 폴더, 템플릿 또는.vsz 파일의 이름입니다. 이 필드는 폴더를 나타내는 데 사용 되는 이름을 수도 있습니다.|  
|{clsidPackage}|에서 지역화 된 문자열, LocalizedName, 설명, IconResourceId, 및 SuggestedBaseName, 예: VSPackage의 위성 동적 연결 라이브러리 (DLL) 리소스에 액세스할 수 있도록 하는 VSPackage의 GUID입니다. IconResourceId는 DLLPath 제공 되지 않은 경우 적용 됩니다. **참고:**  이전 필드의 하나 이상의 리소스 식별자가 아닌 경우이 필드는 선택 사항입니다. 이 필드는 텍스트를 지역화 하지 않는 타사 마법사로 해당 하는.vsdir 파일 일반적으로 비어 있습니다.|  
|LocalizedName|마법사는 템플릿 파일의 지역화 된 이름입니다. 이 필드는 "#ResID" 폼의 리소스 식별자 또는 문자열 수 있습니다. 이 이름은에 표시 되는 **새 항목 추가** 대화 상자입니다. **참고:**  LocalizedName는 리소스 식별자 경우 {clsidPackage}가 필요 합니다.|  
|SortPriority|이 서식 파일 또는 마법사의 상대적 우선 순위를 나타내는 정수입니다. 예를 들어이 항목 1의 값이 있으면이 항목이 항목 옆에 있는 다른 값이 1 및 2 이상은의 정렬 값을 갖는 모든 항목 보다 먼저 표시 됩니다.<br /><br /> 정렬 우선 순위는 동일한 디렉터리에 항목을 기준으로 합니다. 동일한 디렉터리에.vsdir 파일이 여러 개 있을 수 있습니다. 모든 항목 경우에서 *.*해당 디렉터리의 vsdir 파일 병합 됩니다. 동일한 우선 순위를 가진 항목은 표시 되는 이름은 대/소문자 구분 사전적 순서 대로 나열 됩니다.  `_wcsicmp` 함수는 항목을 정렬 하는 데 사용 됩니다.<br /><br /> .Vsdir 파일에 설명 되지 않은 항목에는 우선 순위 번호.vsdir 파일에 나열 된 가장 높은 우선 순위 번호 보다 큰 포함 됩니다. 이러한 항목이 표시 된 목록 이름에 관계 없이 끝날 때 만들어집니다.|  
|설명|마법사는 템플릿 파일의 지역화 된 설명입니다. 이 필드는 "#ResID" 폼의 리소스 식별자 또는 문자열 수 있습니다. 이 문자열에 표시 된 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 항목을 선택 합니다.|  
|DLLPath 또는 {clsidPackage}|서식 파일 또는 마법사에 대 한 아이콘을 로드 하는 데 사용 합니다. 아이콘은.dll 또는.exe 파일을 리소스로 IconResourceId를 사용 하 여 로드 됩니다. 이.dll 또는.exe 파일의 전체 경로 사용 하 여 또는 VSPackage의 GUID를 사용 하 여 식별할 수 있습니다. VSPackage의 DLL 구현 (하지 위성 DLL) 아이콘을 로드할 사용 됩니다.|  
|IconResourceId|DLL 또는 VSPackage 구현 표시할 아이콘을 결정 하는 DLL에서에서 리소스 식별자입니다.|  
|플래그 (<xref:Microsoft.VisualStudio.Shell.Interop.__VSDIRFLAGS>)|사용 하지 않도록 설정 하거나 사용 하도록 설정 하는 데는 **이름** 및 **위치** 필드에 **새 항목 추가** 대화 상자입니다. 값은 **플래그** 필드는 10 진수로 변환 하면 필요한 비트 플래그 조합입니다.<br /><br /> 사용자에 항목을 선택 하는 경우는 **새로** 탭, 프로젝트 이름 필드와 위치 필드에 표시 되는지 여부는 경우 결정은 **새 항목 추가** 대화 상자가 먼저 표시 됩니다. 항목을.vsdir 파일을 통해 제어할 수만 항목을 선택 필드 사용 안 함 및 사용 되는지 여부를 합니다.|  
|SuggestedBaseName|파일, 마법사 또는 서식 파일에 대 한 기본 이름을 나타냅니다. 이 필드는 문자열 또는 폼 "#ResID"의 리소스 식별자는입니다. IDE는 항목에 대 한 기본 이름을 제공 하려면이 값을 사용 합니다. 이 기준 값 MyFile21.asp 같은 고유한 이름이 되도록 하는 정수 값으로 추가 됩니다.<br /><br /> 이전 목록에서 설명, DLLPath, IconResourceId, 플래그 및 SuggestedBaseNumber 템플릿과 마법사 파일에만 적용 됩니다. 이러한 필드에는 폴더에 적용 되지 않습니다. 이 팩트의 BscPrjProjectItems 파일에 코드에 나와 \< EnvSDK>\BscPrj\BscPrj\BscPrjProjectItems 레지스트리 키입니다. 각 레코드에 대 한 4 개의 필드를 사용 하 여 세 개의 레코드 (각 폴더에 대해 하나씩)이이 파일에 포함: RelPathName, {clsidPackage} LocalizedName, 및 SortPriority 합니다.<br /><br /> `General&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#110&#124;100`<br /><br /> `Source_Files&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#111&#124;110`<br /><br /> `Env&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#112&#124;120`|  
  
 마법사 파일을 만들 때 다음 사항을 고려해 야 합니다.  
  
-   의미 있는 데이터가 없는 모든 선택적 필드는 0 (영) 자리 표시자로 포함 되어야 합니다.  
  
-   제공 된 지역화 된 이름이 없는 경우 마법사 파일의 상대 경로 이름을 사용 됩니다.  
  
-   DLLPath clsidPackage 아이콘 위치에 대 한 재정의합니다.  
  
-   정의 된 아이콘이 없는 경우 IDE 해당 확장명을 가진 파일에 대 한 기본 아이콘을 사용 합니다.  
  
-   기본 이름이 없는 경우 '프로젝트에 사용 됩니다.  
  
-   .Vsz 파일, 폴더 또는 템플릿 파일을 삭제 하는 경우에.vsdir 파일에서도 연관 된 레코드를 제거 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [마법사](../../extensibility/internals/wizards.md)   
 [마법사 (합니다. Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)