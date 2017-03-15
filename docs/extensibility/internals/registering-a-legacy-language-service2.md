---
title: "레거시 언어 Service2를 등록 하는 중 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스 등록"
  - "언어 서비스, 레지스트리 정보"
  - "레지스트리, 언어 서비스"
ms.assetid: ca312aa3-f9f1-4572-8553-89bf3a724deb
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# 레거시 언어 서비스를 등록 하는 중
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 섹션에서는 레지스트리 항목의 목록이 다양 한 언어에 대 한 서비스 옵션에서 사용할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 레지스트리 항목의 다음 목록에 *VS Reg 루트* HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\ 같으면*X.Y*, 여기서 *X.Y* 는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 버전 번호입니다.  
  
## 언어 서비스 옵션에 대 한 레지스트리 항목  
 *VS Reg 루트*\\Languages\\Language Services\\*언어 이름* 키에 다음 값이 포함 될 수 있습니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ|*\< GUID \>*|언어 서비스의 GUID입니다.|  
|LangResID|REG\_DWORD|0x0\-0xffff|언어의 지역화 된 텍스트 이름에 대 한 리소스 식별자 \(ResID\)는 문자열입니다.|  
|Package|REG\_SZ|*\< GUID \>*|VSPackage의 GUID입니다.|  
|ShowCompletion|REG\_DWORD|0\-1|지정 여부는 **문 완성** 옵션에 **옵션** 대화 상자가 활성화 됩니다.|  
|ShowSmartIndent|REG\_DWORD|0\-1|지정 하는지 여부를 선택할 수 있는 옵션이 **스마트** 에 들여쓰기는 **옵션** 대화 상자가 활성화 됩니다.|  
|RequestStockColors|REG\_DWORD|0\-1|지정 사용자 지정 여부 또는 기본 색상 키워드 색을 사용 합니다.|  
|ShowHotURLs|REG\_DWORD|0\-1|사용자가 Url을 클릭할 수 있는지 여부를 지정 합니다.|  
|비 핫 Url이 기본값으로 설정|REG\_DWORD|0\-1|에 대 한 초기 설정을 지정 하는 **단일 클릭으로 URL 탐색** 옵션에 **옵션** 대화 상자.|  
|DefaultToInsertSpaces|REG\_DWORD|0\-1|언어 서비스의 기본 탭 옵션으로 "공백 삽입"에 있는지 여부를 지정 합니다.|  
|ShowDropdownBarOption|REG\_DWORD|0\-1|설정 하거나 해제는 **탐색 모음** 옵션에 **옵션** 대화 상자를 표시 하거나 숨기는 **탐색 모음**합니다.|  
|단일 코드 창 에서만|REG\_DWORD|0\-1|설정 하거나 해제는 **새 창** 에 choice는 **창** 언어 서비스에 대 한 메뉴.|  
|EnableAdvancedMembersOption|REG\_DWORD|0\-1|활성화 하거나 비활성화 한 **옵션** 에 대 한 대화 상자 설정을 **고급 멤버 숨기기**합니다.|  
|CF\_HTML 지원|REG\_DWORD|0\-1|복사 및 붙여넣기 HTML 데이터 편집기를 활성화 하는지 여부를 지정 합니다.|  
|EnableLineNumbersOption|REG\_DWORD|0\-1|지정 여부는 **줄 번호를** 옵션에 **옵션** 언어 서비스에 대 한 대화 상자가 활성화 됩니다.|  
|HideAdvancedMembersByDefault|REG\_DWORD|0\-1|완성 목록에 전용 필드와 같은 고급 멤버를 숨길지 여부를 지정 합니다.|  
|ShowBraceCompletion|REG\_DWORD|0\-1|지정 여부는 **중괄호 완성** 옵션에 **옵션** 대화 상자가 활성화 됩니다.|  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      C/C++\  
        (Default)             = reg_sz:{B2F072B0-ABC1-11D0-9D62-00C04FD9DFD9}  
        LangResID             = reg_dword:0x00000000  
        Package               = reg_sz:{8C2EA640-ABC1-11D0-9D62-00C04FD9DFD9}  
        ShowCompletion        = reg_dword:0x00000001  
        ShowSmartIndent       = reg_dword:0x00000001  
        ShowDropdownBarOption = reg_dword:0x00000001  
```  
  
## 디버거 언어 옵션에 대 한 레지스트리 항목  
 *VS Reg 루트*\\Languages\\Language Services\\*언어 이름*\\Debugger Languages\\*GUID*\\ 키 다음 값을 포함할 수 있습니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ|텍스트|기본값은 문서 언어의 이름 데 사용할 수 있습니다. 이 키의 이름에 해당 하는 항목이 있는 식 계산기의 GUID는 *\< VS Reg 루트 \>*\\AD7Metrics\\Expression 계산기입니다.|  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      C/C++\  
        Debugger Languages\  
          {3A12D0B7-C26C-11D0-B442-00A0244A1DD2}\  
            (Default) = reg_sz:C++  
```  
  
## 편집기 도구 옵션에 대 한 레지스트리 항목  
 속성 페이지 및 속성 노드에 대 한 EditorToolsOptions 키 아래에 레지스트리 키를 추가할 수 있습니다. 이러한 키와 해당 값의 속성 페이지를 식별는 **옵션** 대화 상자 \(에 **도구** 메뉴\) 언어 서비스를 구성 하는 데 사용 됩니다. 다음 예에서 *페이지 이름* 속성 페이지의 이름 및 *노드 이름* 은 트리에서 노드 이름에는 **옵션** 대화 상자. 페이지 항목과 노드를 개별적으로 지정 되어야 합니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ|ResID|이 옵션 페이지의 지역화 된 표시 이름입니다. 리터럴 텍스트 또는 \# 이름을 수`nnn`, 여기서 `nnn` 위성 DLL의 지정 된 VSPackage에에서 문자열 리소스 ID입니다.|  
|Package|REG\_SZ|*GUID*|이 옵션 페이지를 구현 하는 VSPackage의 GUID입니다.|  
|페이지|REG\_SZ|*GUID*|속성 페이지의 GUID를 호출 하 여 VSPackage에서 요청 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> 메서드. 이 레지스트리 항목이 없으면 페이지가 아닌 노드를 레지스트리 키에 설명 합니다.|  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      CSharp\  
        EditorToolsOptions\  
          Formatting\  
            (Default) = reg_sz:#242  
            Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
            General\  
              (Default) = reg_sz:#255  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{3EB2CC0B-033E-4D75-B26A-B2362C25227E}  
            Indentation\  
              (Default) = reg_sz:#250  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{5E21D017-6D2A-4114-A1F1-C923F001CBBB}  
            Newlines\  
              (Default) = reg_sz:#253  
              Package   = reg_sz:{A066E284-DCAB-11D2-B551-00C04F68D4DB}  
              Page      = reg_sz:{607D8062-68D1-41E4-9A35-B5E7F14D0481}  
```  
  
## 파일 이름 확장명 옵션에 대 한 레지스트리 항목  
 파일 확장명에 대 한 항목의 앞에 마침표, 예를 들어 ".myext"를 포함 해야 합니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ|*GUID*|이 파일 확장명 형식에 대 한 기본 언어 서비스에 대 한 서비스 GUID입니다.|  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    File Extensions\  
      .cpp\  
        (Default) = {B2F072B0-ABC1-11D0-9D62-00C04FD9DFD9}  
```  
  
## 편집기 옵션에 대 한 레지스트리 항목  
 *VS Reg 루트*\\Editors 키에 다음 값이 포함 될 수 있습니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ|""|사용 되지 않습니다. 설명서에 대 한 여기에 이름을 입력할 수 있습니다.|  
|DefaultToolboxTab|REG\_SZ|""|편집기가 활성화 하는 경우 기본값으로 설정 하려면 도구 상자 탭의 이름입니다.|  
|DisplayName|REG\_SZ|ResID|에 표시할 이름을 **Open With** 대화 상자입니다. 이름이 표준 형식 문자열 리소스 ID 또는 이름입니다.|  
|ExcludeDefTextEditor|REG\_DWORD|0\-1|에 사용 되는 **Open With** 메뉴 명령입니다. 특정 파일 형식에 대해 사용할 수 있는 편집기의 목록에서 기본 텍스트 편집기를 나열 하지 않을 경우이 값을 1로 설정 합니다.|  
|LinkedEditorGUID|REG\_SZ|*\< GUID \>*|코드 페이지 지원 파일을 열 수 있는 모든 언어 서비스에 사용 합니다. 예를 들어.txt 파일을 사용 하 여 열면는 **연결** 명령 및 인코딩 없이 소스 코드 편집기를 사용 하기 위한 옵션이 제공 됩니다.<br /><br /> 하위 키의 이름으로 지정 된 GUID는 코드 페이지 편집기 팩터리의; 이 특정 레지스트리 항목에 지정 된 연결 된 GUID 일반 편집기 팩터리입니다. 이 항목의 목적은 IDE의 기본 편집기를 사용 하 여 파일이 열리지 않으면, IDE 편집기를 사용 하는 다음 목록에서 시도 합니다. 다음이 편집기는이 편집기 팩터리는 기본적으로 실패 한 편집기 팩터리와 동일 하기 때문에 코드 페이지 편집기 팩터리 되지 않아야 합니다.|  
|Package|REG\_SZ|*\< GUID \>*|VSPackage GUID ResID 표시 이름입니다.|  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      (Default)            = reg_sz:Html Editor with Encoding  
      DefaultToolboxTab    = reg_sz:HTML  
      DisplayName          = reg_sz:#20101  
      LinkedEditorGUID     = reg_sz:{C76D83F8-A489-11D0-8195-00A0C91BBEE3}  
      Package              = reg_sz:{1B437D20-F8FE-11D2-A6AE-00104BCC7269}  
```  
  
## 논리적 보기 옵션에 대 한 레지스트리 항목  
 *VS Reg 루트*\\Editors\\*편집기 GUI \>*\\LogicalViews 키에 다음 값이 포함 될 수 있습니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ||사용 되지 않습니다.|  
|*\< GUID \>*|REG\_SZ|""|지 원하는 논리 뷰에 키입니다. 필요에 따라 이들 중 대부분을 사용할 수 있습니다. 레지스트리 항목의 이름, 중요 한 것은 값이 아닌은 항상 빈 문자열입니다.|  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      LogicalViews\  
       (Default) = reg_sz:  
       {7651a700-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a701-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a702-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
       {7651a703-06e5-11d1-8ebd-00a0c90f26ea} = reg_sz:  
```  
  
## 편집기 확장 옵션에 대 한 레지스트리 항목  
 *VS Reg 루트*\\Editors\\*편집기 GUID*\\Extensions 키에 다음 값이 포함 될 수 있습니다. 파일 이름 확장명에는 앞에 마침표가 포함 되지 않습니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|\(기본값\)|REG\_SZ||사용 되지 않습니다.|  
|*\< 확장 \>*|REG\_DWORD|0\-0xffffffff|확장의 상대적 우선 순위입니다. 두 개 이상의 언어 같은 확장 프로그램을 공유 하는 경우 우선 순위가 높은 언어 선택 됩니다.|  
  
 또한 편집기에 대 한 현재 사용자의 기본 선택 HKEY\_Current\_User\\Software\\Microsoft\\VisualStudio\\에 저장 됩니다*X.Y*\\Default Editors\\*ext*합니다. 사용자 지정 항목에는 선택한 언어 서비스의 GUID입니다. 현재 사용자에 대 한 우선 순위를 열립니다.  
  
### 예제  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\  
  \Editors\  
    {8281C572-2171-45AA-A642-7D8BC1662F1C}\  
      Extensions\  
       (Default) = reg_sz:  
       *         = reg_dword:0x00000018  
       html      = reg_dword:0x00000027  
       shtm      = reg_dword:0x00000027  
       shtml     = reg_dword:0x00000027  
```  
  
## 관리 되는 패키지 프레임 워크 언어 서비스 옵션에 대 한 레지스트리 항목  
 다음 레지스트리 항목 관리 되는 패키지 프레임 워크 \(MPF\) 언어 서비스 클래스와 관련이 있습니다. 이러한 레지스트리 항목에는 기타 고급 편집 기능에 대 한 다양 한 IntelliSense 기능에 대 한 언어 서비스의 지원을 나타냅니다.  
  
 이러한 레지스트리 항목을 통해 액세스 되는 <xref:Microsoft.VisualStudio.Package.LanguagePreferences> 클래스입니다.  
  
|이름|형식|범위|설명|  
|--------|--------|--------|--------|  
|CodeSense|REG\_DWORD|0\-1|IntelliSense 작업을 지원 합니다.|  
|MatchBraces|REG\_DWORD|0\-1|일치 하는 중괄호, 괄호 및 대괄호와 같은 언어 쌍에 대 한 지원.|  
|QuickInfo|REG\_DWORD|0\-1|IntelliSense 요약 정보 작업에 대 한 지원입니다.|  
|ShowMatchingBrace|REG\_DWORD|0\-1|상태 표시줄에 일치 하는 언어 쌍을 표시 하기 위한 지원 합니다.|  
|MatchBracesAtCaret|REG\_DWORD|0\-1|일반적으로 두 개의 요소를 강조 표시를 통해 일치 하는 언어 쌍을 표시 하는 것에 대 한 지원.|  
|MaxErrorMessages|REG\_DWORD|0\-n|에 표시 될 수 있는 오류의 최대 수는 **오류 목록** 창입니다.|  
|CodeSenseDelay|REG\_DWORD|0\-n|백그라운드 IntelliSense 작업에 대 한 구문 분석을 시작 하기 전에 지연할 시간 \(밀리초\)의 수입니다.|  
|EnableAsyncCompletion|REG\_DWORD|0\-1|백그라운드 구문 분석 지원입니다.|  
|EnableCommenting|REG\_DWORD|0\-1|선택한 텍스트 블록의 주석 지원 하 고 선택한 텍스트를 주석 처리 제거에 대 한 지원을 포함 하 고 있습니다.|  
|EnableFormatSelection|REG\_DWORD|0\-1|자동 들여쓰기 등의 텍스트 서식 지정 또는 중괄호 위치 조정에 대 한 지원.|  
|AutoOutlining|REG\_DWORD|0\-1|개요 \(축소할 수 있는 영역\)에 대 한 지원.|  
|MaxRegions|REG\_DWORD|0\-n|숨겨진된 영역의 각 파일의 최대 수입니다.|  
  
```  
ExampleHKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\  
  Languages\  
    Language Services\  
      XML\  
        (Default)             = reg_sz:{f6819a78-a205-47b5-be1c-675b3c7f0b8e}  
        MatchBraces           = reg_dword:0x00000001  
        QuickInfo             = reg_dword:0x00000001  
        ShowMatchingBrace     = reg_dword:0x00000001  
        MatchBracesAtCaret    = reg_dword:0x00000000  
        MaxErrorMessages      = reg_dword:0x00000064  
        CodeSenseDelay        = reg_dword:0x000001f4  
        MaxRegions            = reg_dword:0x0000000a  
```  
  
## 참고 항목  
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)