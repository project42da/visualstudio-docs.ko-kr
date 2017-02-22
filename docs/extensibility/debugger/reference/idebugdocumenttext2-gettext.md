---
title: "IDebugDocumentText2::GetText | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentText2::GetText"
helpviewer_keywords: 
  - "IDebugDocumentText2::GetText"
ms.assetid: f8c15a58-da77-473e-a721-7a094e306c63
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentText2::GetText
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서의 지정 된 위치에서 텍스트를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetText(   
   TEXT_POSITION pos,  
   ULONG         cMaxChars,  
   WCHAR*        pText,  
   ULONG*        pcNumChars  
);  
```  
  
```c#  
int GetText(   
   eumn_TEXT_POSITION pos,  
   uint               cMaxChars,  
   IntPtr             pText,  
   out uint           pcNumChars  
);  
```  
  
#### 매개 변수  
 `pos`  
 \[in\] A [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 검색 해야 하는 텍스트의 위치를 나타내는 구조입니다.  
  
 `cMaxChars`  
 \[in\] 검색할 텍스트 문자의 최대 개수입니다.  
  
 `pText`  
 \[in, out\] 원하는 텍스트 사용 하 여 입력 버퍼에 대 한 포인터입니다.  이 버퍼 적어도 포함할 수 있어야 합니다. `cMaxChars` 의 와이드 문자 수입니다.  
  
 `pcNumChars`  
 \[out\] 실제로 검색 문자 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 어떻게이 메서드 C\#를 호출할 수 있습니다 보여 주는이 예제입니다.  
  
```c#  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace Mynamespace  
{  
    class MyClass  
    {  
         string GetDocumentText(IDebugDocumentText2 pText, TEXT_POSITION pos)  
        {  
             string documentText = string.Empty;  
             if (pText != null)  
             {  
                  uint numLines = 0;  
                  uint numChars = 0;  
                  int hr;  
                  hr = pText.GetSize(ref numLines, ref numChars);  
                  if (ErrorHandler.Succeeded(hr))  
                  {  
                       IntPtr buffer = Marshal.AllocCoTaskMem((int)numChars * sizeof(char));  
                       uint actualChars = 0;  
                       hr = pText.GetText(pos, numChars, buffer, out actualChars);  
                       if (ErrorHandler.Succeeded(hr))  
                       {  
                            documentText = Marshal.PtrToStringUni(buffer, (int)actualChars);  
                       }  
                       Marshal.FreeCoTaskMem(buffer);  
                  }  
              }  
              return documentText;  
         }  
    }  
}  
```  
  
## 참고 항목  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)