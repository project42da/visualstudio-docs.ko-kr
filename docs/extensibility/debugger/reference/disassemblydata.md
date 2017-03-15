---
title: "DisassemblyData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DisassemblyData"
helpviewer_keywords: 
  - "DisassemblyData 구조"
ms.assetid: 10e70aa7-9381-40d3-bdd1-d2cad78ef16c
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# DisassemblyData
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

표시 하는 통합된 개발 환경 \(IDE\)에 대 한 하나의 디스어셈블리 명령을 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagDisassemblyData {   
   DISASSEMBLY_STREAM_FIELDS dwFields;  
   BSTR                      bstrAddress;  
   BSTR                      bstrAddressOffset;  
   BSTR                      bstrCodeBytes;  
   BSTR                      bstrOpcode;  
   BSTR                      bstrOperands;  
   BSTR                      bstrSymbol;  
   UINT64                    uCodeLocationId;  
   TEXT_POSITION             posBeg;  
   TEXT_POSITION             posEnd;  
   BSTR                      bstrDocumentUrl;  
   DWORD                     dwByteOffset;  
   DISASSEMBLY_FLAGS         dwFlags;  
} DisassemblyData;  
```  
  
```c#  
public struct DisassemblyData {   
   public uint          dwFields;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrCodeBytes;  
   public string        bstrOpcode;  
   public string        bstrOperands;  
   public string        bstrSymbol;  
   public ulong         uCodeLocationId;  
   public TEXT_POSITION posBeg;  
   public TEXT_POSITION posEnd;  
   public string        bstrDocumentUrl;  
   public uint          dwByteOffset;  
   public uint          dwFlags;  
};  
```  
  
## Members  
 `dwFields`  
 [DISASSEMBLY\_STREAM\_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) 채워진 필드를 지정 하는 상수입니다.  
  
 `bstrAddress`  
 일부 시작 위치 \(일반적으로 연관 된 함수 부분\)에서 오프셋으로 주소입니다.  
  
 `bstrCodeBytes`  
 이 명령에 대해 코드 바이트 수입니다.  
  
 `bstrOpcode`  
 이 명령에 대 한 opcode입니다.  
  
 `bstrOperands`  
 이 명령에 대 한 피연산자입니다.  
  
 `bstrSymbol`  
 기호 이름이 있는 경우 주소 \(공용 기호, 레이블 등\)와 관련 된.  
  
 `uCodeLocationId`  
 이 분해 된 줄의 코드 위치 식별자입니다.  다음 한 줄의 코드가 컨텍스트 주소 다른 컨텍스트의 코드 주소 보다 클 경우 디스어셈블된 코드 위치 식별자의 첫 번째도 두 번째 코드 위치 식별자 보다 크면 안 됩니다.  
  
 `posBeg`  
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 디스어셈블리 데이터가 시작 되는 위치에 위치에서 문서에 해당 합니다.  
  
 `posEnd`  
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 문서에서 디스어셈블리 데이터 끝나는 위치에 해당 합니다.  
  
 `bstrDocumentUrl`  
 파일 이름으로 표현 될 수 있습니다 텍스트 문서에 대 한의 `bstrDocumentUrl` 필드 위치 원본을 찾을 수 있습니다, 파일 이름에 포함 된 형식을 사용 하 여  `file://file 이름`.  
  
 파일 이름으로 표시 될 수 없는 텍스트 문서에 대 한 `bstrDocumentUrl` 문서에 대 한 고유 식별자 이며 디버그 엔진 구현 해야는 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md) 메서드.  
  
 체크섬에 대 한 자세한 정보가이 필드에 포함 될 수도 있습니다.  에 대 한 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `dwByteOffset`  
 코드 줄의 시작 부분에서 명령입니다 바이트 수입니다.  
  
 `dwFlags`  
 [DISASSEMBLY\_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md) 활성 플래그를 지정 하는 상수입니다.  
  
## 설명  
 각 `DisassemblyData` 구조 디스어셈블리 명령에 설명 합니다.  이러한 구조의 배열 로부터 반환 되는 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) 메서드.  
  
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조는 텍스트 기반 문서에 대해서만 사용 됩니다.  이 명령에 대 한 소스 코드 범위 예 문이나 줄에서 생성 된 첫 번째 명령에 대 한만 채울 때, `dwByteOffset == 0`.  
  
 아닌 있는 문서의 경우 문서 컨텍스트 코드를 얻을 수 있습니다 및 해당 `bstrDocumentUrl` 필드 null 값 이어야 합니다.  경우는 `bstrDocumentUrl` 필드와 동일는 `bstrDocumentUrl` 필드 이전에 `DisassemblyData` 배열 요소를 다음 설정의 `bstrDocumentUrl` null 값입니다.  
  
 경우는 `dwFlags` 필드는 `DF_DOCUMENT_CHECKSUM` 추가 체크섬 정보 포인터가 가리키는 문자열 뒤에 오는 다음 플래그 집합을는 `bstrDocumentUrl` 필드입니다.  특히 null 문자열 종료 문자 뒤는 차례로 체크섬 바이트 수를 나타내는 4 바이트 값으로 오며 차례로 체크섬 바이트 뒤에 체크섬 알고리즘을 식별 하는 GUID는 다음과 같습니다.  인코딩 및 디코딩이 필드에 방법에이 항목의 예제를 참조 하십시오. [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)].  
  
## 예제  
 `bstrDocumentUrl` 필드 경우 문자열 이외의 추가 정보를 포함할 수 있습니다의 `DF_DOCUMENT_CHECKSUM` 플래그가 설정 되었습니다.  만들고이 인코딩된 문자열을 읽는 과정에서 간단 [!INCLUDE[vcprvc](../../../debugger/includes/vcprvc_md.md)].  그러나, [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)], 다른 문제입니다.  사람들에 대해 궁금할 것입니다, 다음 예제에서는 인코딩된 문자열을 작성 하는 방법을 보여 줍니다 [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)] 하 고 인코딩된 문자열을 디코딩 하는 한 가지 방법은 [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)].  
  
```c#  
using System;  
using System.Runtime.InteropServices;  
  
namespace MyNamespace  
    class MyClass  
    {  
        string EncodeData(string documentString,  
                          Guid checksumGuid,  
                          byte[] checksumData)  
        {  
            string returnString = documentString;  
  
            if (checksumGuid == null || checksumData == null)  
            {  
                // Nothing more to do. Just return the string.  
                return returnString;  
            }  
  
            returnString += '\0'; // separating null value  
  
            // Add checksum GUID to string.  
            byte[] guidDataArray  = checksumGuid.ToByteArray();  
            int    guidDataLength = guidDataArray.Length;  
            IntPtr pBuffer        = Marshal.AllocCoTaskMem(guidDataLength);  
            for (int i = 0; i < guidDataLength; i++)  
            {  
                Marshal.WriteByte(pBuffer, i, guidDataArray[i]);  
            }  
            // Copy guid data bytes to string as wide characters.  
            // Assumption: sizeof(char) == 2.  
            for (int i = 0; i < guidDataLength; i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
  
            // Add checksum count (a 32-bit value).  
            Int32 checksumCount = checksumData.Length;  
            Marshal.StructureToPtr(checksumCount, pBuffer, true);  
            for (int i = 0; i < sizeof(Int32) / sizeof(char); i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
  
            // Add checksum data.  
            pBuffer = Marshal.AllocCoTaskMem(checksumCount);  
            for (int i = 0; i < checksumCount; i++)  
            {  
                Marshal.WriteByte(pBuffer, i, checksumData[i]);  
            }  
            for (int i = 0; i < checksumCount / sizeof(char); i++)  
            {  
                returnString += (char)Marshal.ReadInt16(pBuffer, i * sizeof(char));  
            }  
            Marshal.FreeCoTaskMem(pBuffer);  
  
            return returnString;  
        }  
  
        void DecodeData(    string encodedString,  
                        out string documentString,  
                        out Guid   checksumGuid,  
                        out byte[] checksumData)  
       {  
           documentString = String.Empty;  
           checksumGuid = Guid.Empty;  
           checksumData = null;  
  
           IntPtr pBuffer = Marshal.StringToBSTR(encodedString);  
           if (null != pBuffer)  
           {  
               int bufferOffset = 0;  
  
               // Parse string out.  String is assumed to be Unicode.  
               documentString = Marshal.PtrToStringUni(pBuffer);  
               bufferOffset += (documentString.Length + 1) * sizeof(char);  
  
               // Parse Guid out.  
               // Read guid bytes from buffer and store in temporary  
               // buffer that contains only the guid bytes. Then the  
               // Marshal.PtrToStructure() can work properly.  
               byte[] guidDataArray  = checksumGuid.ToByteArray();  
               int    guidDataLength = guidDataArray.Length;  
               IntPtr pGuidBuffer    = Marshal.AllocCoTaskMem(guidDataLength);  
               for (int i = 0; i < guidDataLength; i++)  
               {  
                   Marshal.WriteByte(pGuidBuffer, i,  
                                     Marshal.ReadByte(pBuffer, bufferOffset + i);  
               }  
               bufferOffset += guidDataLength;  
               checksumGuid = (Guid)Marshal.PtrToStructure(pGuidBuffer, typeof(Guid));  
               Marshal.FreeCoTaskMem(pGuidBuffer);  
  
              // Parse out the number of checksum data bytes (always 32-bit value).  
              int dataCount = Marshal.ReadInt32(pBuffer, bufferOffset);  
              bufferOffset += sizeof(Int32);  
  
              // Parse out the checksum data.  
              checksumData = new byte[dataCount];  
              for (int i = 0; i < dataCount; i++)  
              {  
                  checksumData[i] = Marshal.ReadByte(pBuffer, bufferOffset + i);  
              }  
           }  
       }  
    }  
}  
```  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY\_STREAM\_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [TEXT\_POSITION](../../../extensibility/debugger/reference/text-position.md)   
 [DISASSEMBLY\_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)