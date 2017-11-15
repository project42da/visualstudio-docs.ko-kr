---
title: "VSTU에서 만든 프로젝트 파일 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60b8cc1d-cacc-404d-b768-77e81bc354f8
caps.latest.revision: "2"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: d4447d0228cbf446d3376db96c5e23f795c9cf86
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="customize-project-files-created-by-vstu"></a>VSTU에서 만든 프로젝트 파일 사용자 지정
Visual Studio Tools for Unity는 프로젝트 파일을 생성하는 동안 Unity 스타일의 콜백을 제공합니다. `VisualStudioIntegration.ProjectFileGeneration` 이벤트로 등록하여 다시 생성될 때마다 프로젝트 파일을 수정합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 Visual Studio Tools for Unity에서 생성한 Visual Studio 프로젝트 파일을 사용자 지정하는 방법  
  
## <a name="example"></a>예제  
  
```csharp  
using System;  
using System.IO;  
using System.Linq;  
using System.Text;  
using System.Xml.Linq;  
  
using UnityEngine;  
using UnityEditor;  
  
using SyntaxTree.VisualStudio.Unity.Bridge;  
  
[InitializeOnLoad]  
public class ProjectFileHook  
{  
    // necessary for XLinq to save the xml project file in utf8  
    class Utf8StringWriter : StringWriter  
    {  
        public override Encoding Encoding  
        {  
            get { return Encoding.UTF8; }  
        }  
    }  
  
    static ProjectFileHook()  
    {  
        ProjectFilesGenerator.ProjectFileGeneration += (string name, string content) =>  
        {  
            // parse the document and make some changes  
            var document = XDocument.Parse(content);  
            document.Root.Add(new XComment("FIX ME"));  
  
            // save the changes using the Utf8StringWriter  
            var str = new Utf8StringWriter();  
            document.Save(str);  
  
            return str.ToString();  
        };  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [예제: 로그 콜백](../cross-platform/share-the-unity-log-callback-with-vstu.md)