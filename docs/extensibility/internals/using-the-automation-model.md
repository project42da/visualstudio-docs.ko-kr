---
title: "자동화 모델을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 82a9c2068bdd3e234bcc53ffa870ca289289d690
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="using-the-automation-model"></a>자동화 모델을 사용 하 여
속성 및 메서드를 호출 하 여 얻을 수 자동화에 VSPackage를 연결한 후의 <xref:EnvDTE.DTEClass.GetObject%2A> 에서 메서드는 <xref:EnvDTE._DTE> 개체를 검색 하려면 개체를 나타내는 문자열을 전달 합니다.  
  
## <a name="obtaining-project-objects"></a>프로젝트 개체 가져오기  
 자동화 소비자를 얻는 방법을 프로젝트 자동화 개체를 보여 주는 두 개의 코드 예는 다음과 같습니다. DTE 개체를 가져오는 방법에 대 한 정보를 참조 하십시오. [하는 방법: DTE 및 DTE2 개체에 대 한 참조 가져오기](http://msdn.microsoft.com/Library/c92e3c8e-82e6-4a67-85da-e43c50ffd8e4)합니다.  
  
```vb  
Sub DoAutomation()  
    Dim MyProjects As Projects  
    MyProjects = DTE.GetObject("AcmeProject")  
End Sub  
```  
  
```cpp  
void DoAutomation(void)  
{  
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.  
    pMyPkg = pDTE->GetObject("AcmeProjects");   
  
   // The '=' performs a Query Interface.  
   // Assumes pDTE is already available as a global.  
   // Use pMyPkg to access your projects object's properties and methods.  
}  
  
```  
  
 이 시점에서 특정 계층 모델 아래로 이동 하려면 VSPackage의 일부인 표준 프로젝트 개체를 사용할 수 있습니다.  
  
 다음 코드 예제에는 사용자 지정 프로젝트 유형의 속성은 사용자 지정 개체를 가져오는 방법을 보여 줍니다.:  
  
```vb  
Dim MyPrj As Project  
Dim MyPrjItem As ProjectItem  
Dim objMyObject as MyExtendedObject  
  
MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project  
objMyObject = MyPrj.Object 'You call .Object to get to special Project  
                           'implementation  
objMyObject.MySpecialMethodOrProperty  
```  
  
 모든 속성의 이름을 나열 하는 다음 코드는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경 **일반** 옵션에 **도구** 메뉴:  
  
```vb  
dim objDTE  
dim objEnv  
set objDTE = CreateObject("VisualStudio.DTE")  
set objEnv = objDTE.Properties("Environment", "General")  
for each obj in ObjEnv  
MsgBox obj.Name  
Next  
  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:EnvDTE.DTEClass.GetObject%2A>
