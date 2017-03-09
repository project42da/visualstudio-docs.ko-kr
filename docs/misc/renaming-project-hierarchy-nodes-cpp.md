---
title: "프로젝트 계층 구조 노드 이름 바꾸기(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "HierUtil7 샘플[Visual Studio SDK], 프로젝트 노드 이름 바꾸기"
  - "프로젝트 노드, HierUtil7 샘플에서 이름 바꾸기"
ms.assetid: cea5968e-e9f8-41a5-b068-622df542247c
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 프로젝트 계층 구조 노드 이름 바꾸기(C++)
관리 되지 않는 c \+ \+에 대 한 HierUtil7 프로젝트 프레임 워크를 사용 하 여 프로젝트 폴더 계층 구조 노드 이름을 바꿀 수 있습니다.  자세한 내용은 [HierUtil7 Sample](http://msdn.microsoft.com/ko-kr/29c15184-a70c-4813-86c2-fb1d47442d11)를 참조하십시오.  
  
## 계층 구조 노드를 확장합니다.  
  
#### 계층 구조 노드를 확장 하 고 폴더 이름 바꾸기  
  
1.  다음 메서드를 사용 하 여 계층 구조 노드를 선택 합니다.  
  
    ```  
    IfFailGo(pNode->ExtExpand(EXPF_SelectItem, GUID_MacroExplorer));  
    ```  
  
     `pNode`폴더에 해당 하는 계층 구조 컨테이너입니다 및 `EXPF_SelectItem` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.EXPANDFLAGS> 열거형입니다.  `GUID_MacroExplorer` Vsshell.idl에 정의 된 GUID 상수가 고 예를 들어 `rguidPersistenceSlot` 의 함수 시그니처에서 `ExtExpand`hu\_node.h에 정의 된.  
  
    ```  
    HRESULT ExtExpand(EXPANDFLAGS expandflags, REFGUID rguidPersistenceSlot = GUID_SolutionExplorer) const;  
    ```  
  
     \< 설치 루트 \> \\Program Files\\VSIP 8.0\\EnvSDK\\common\\hierutil7 폴더에서 Hu\_node.h 파일을 찾을 수 있습니다.  
  
2.  이름 바꾸기 명령을 사용 하 여 게시 하 여 폴더를 이름을 바꿉니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.PostExecCommand%2A>  
  
    ```  
    IfFailGo(srpVsUIShell->PostExecCommand(&guidVSStd97, cmdidRename, 0, NULL));  
    ```  
  
     `srpVsUIShell`is a <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> pointer: `<IVsUIShell>``srpVsUIShell`.  `guiVSStd97`명령 그룹에 고유 식별자가 명령 `cmdidRename` 정의 vsshlids.h에 속하는.  
  
## 참고 항목  
 [프로젝트 형식 만들기](../extensibility/internals/creating-project-types.md)   
 [VSSDK 샘플](../misc/vssdk-samples.md)