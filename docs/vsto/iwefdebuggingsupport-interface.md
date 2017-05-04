---
title: "IWefDebuggingSupport 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 0bd1c6a6-67a5-4478-b942-8b937b28f723
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# IWefDebuggingSupport 인터페이스
  Visual Studio에 대 한 Office 응용 프로그램의 디버깅을 돕기 위해, 같은 디버깅 환경에서 구현 합니다.  Word 또는 Excel과 같은 Office 응용 프로그램에서 Visual Studio이 인터페이스를 가져옵니다 하 고 메서드 인터페이스 특정 시점에서 디버깅 세션 동안를 호출 합니다.  
  
## 구문  
  
```  
[  
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),  
    oleautomation  
]  
interface IWefDebuggingSupport : IUnknown  
{  
    HRESULT SetWefProcessId(  
        [in] DWORD dwProcessId);  
    HRESULT GetAutoInsertExtensions(  
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);  
}  
```  
  
## 메서드  
 메서드는 다음 표에 나와 있는 IWefDebuggingSupport 인터페이스를 정의 합니다.  
  
|Name|설명|  
|----------|--------|  
|[GetAutoInsertExtensions 메서드](../vsto/getautoinsertextensions-method.md)|디버깅 하는 동안 자동으로 삽입 하는 office 응용 프로그램에 대 한 정보를 가져옵니다.|  
|[SetWefProcessId 메서드](../vsto/setwefprocessid-method.md)|웹 확장 프레임 워크 \(WEF\) 콘텐츠를 실행 하는 프로세스 id를 제공 합니다.|  
  
  