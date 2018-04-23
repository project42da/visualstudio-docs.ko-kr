---
title: DisassemblyData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DisassemblyData
helpviewer_keywords:
- DisassemblyData structure
ms.assetid: 10e70aa7-9381-40d3-bdd1-d2cad78ef16c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4276009244f1d49b89311d5d158a34bebf3fcf23
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="disassemblydata"></a>DisassemblyData
표시할 통합된 개발 환경 (IDE)에 대 한 하나의 디스어셈블리 명령에 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
## <a name="members"></a>멤버  
 `dwFields`  
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) 채워진 필드를 지정 하는 상수입니다.  
  
 `bstrAddress`  
 몇 가지 시작 지점 (일반적으로 연결 된 함수의 시작) 로부터의 오프셋으로 주소입니다.  
  
 `bstrCodeBytes`  
 이 명령에 대해 코드 바이트입니다.  
  
 `bstrOpcode`  
 이 명령에 대해 opcode입니다.  
  
 `bstrOperands`  
 이 명령에 대 한 피연산자입니다.  
  
 `bstrSymbol`  
 기호 이름이 있는 경우 연관 된 주소 (공용 기호, 레이블 및 등).  
  
 `uCodeLocationId`  
 이 코드 위치 식별자 줄을 디스어셈블합니다. 한 줄의 코드 컨텍스트 주소를 다른 형식의 코드 컨텍스트 주소 보다 큰 다음 디스어셈블된 코드 위치 식별자의 첫 번째 두 번째 코드 위치 식별자 보다 클 수도 있습니다.  
  
 `posBeg`  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 디스어셈블리 데이터가 시작 되는 문서에서 위치에 해당 하는 합니다.  
  
 `posEnd`  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 디스어셈블리 데이터 끝나는 문서에서 위치에 해당 하는 합니다.  
  
 `bstrDocumentUrl`  
 파일 이름으로 나타낼 수 있는 텍스트 문서에 대 한는 `bstrDocumentUrl` 소스를 찾을 수 있는, 파일 이름 필드는 채웁니다는 형식을 사용 하 여 `file://file name`합니다.  
  
 파일 이름으로 표현할 수 없는 텍스트 문서에 대 한 `bstrDocumentUrl` 는 문서에 대 한 고유 식별자 이며 디버그 엔진 구현 해야 합니다는 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md) 메서드.  
  
 이 필드는 체크섬에 대 한 추가 정보를 포함할 수도 있습니다. 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `dwByteOffset`  
 명령 코드 줄의 시작 부분에서 바이트 수입니다.  
  
 `dwFlags`  
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md) 활성는 플래그를 지정 하는 상수입니다.  
  
## <a name="remarks"></a>설명  
 각 `DisassemblyData` 구조 디스어셈블리의 명령에 설명 합니다. 이러한 구조체의 배열에서 반환 되는 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) 메서드.  
  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조 텍스트 기반 문서에만에 사용 됩니다. 예를 들어 문이나 줄에서 생성 된 첫 번째 명령에 대해서만이 명령에 대 한 소스 코드 범위 입력, `dwByteOffset == 0`합니다.  
  
 문서는 텍스트가 아닌에 대 한 문서 컨텍스트에서에서 얻을 수 있습니다는 코드와 `bstrDocumentUrl` 필드에 null 값 이어야 합니다. 경우는 `bstrDocumentUrl` 필드와 같습니다는 `bstrDocumentUrl` 필드에 이전 `DisassemblyData` 배열 요소를 설정 합니다.는 `bstrDocumentUrl` null 값으로.  
  
 경우는 `dwFlags` 필드에는 `DF_DOCUMENT_CHECKSUM` 플래그가 설정, 추가 체크섬 정보에서 가리키는 문자열 뒤에 나오는 다음는 `bstrDocumentUrl` 필드입니다. 특히, null 문자열 종결자 후 있습니다 뒤에 오는 체크섬의 바이트 수를 나타내는 4 바이트 값으로 다시 다음 하 고 차례로 뒤에 체크섬 바이트 체크섬 알고리즘을 식별 하는 GUID입니다. 인코딩 및 디코딩이 필드에서 하는 방법에이 항목의 예제를 참조 하십시오. [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)]합니다.  
  
## <a name="example"></a>예제  
 `bstrDocumentUrl` 경우 필드 문자열 이외의 추가 정보를 포함 될 수는 `DF_DOCUMENT_CHECKSUM` 플래그가 설정 되어 있습니다. 만들고이 인코딩된 문자열을 읽는 간단에서 [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]합니다. 그러나 [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)], 다른 문제를입니다. 사용자를 위해 자세한 내용을 보려면, 다음 예제에서는에서 인코딩된 문자열을 만드는 한 가지 방법은 [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)] 에서 인코딩된 문자열을 디코딩하는 한 가지 방법은 및 [!INCLUDE[csprcs](../../../data-tools/includes/csprcs_md.md)]합니다.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
namespace MyNamespace  
{
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
            for (int i = 0; i < guidDataLength / sizeof(char); i++)  
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
                                     Marshal.ReadByte(pBuffer, bufferOffset + i));  
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
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)
