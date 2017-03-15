---
title: "__pin | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__pin"
  - "__pin_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "고정 포인터 __pin 키워드"
  - "관리되지 않는 형식"
  - "__pin 키워드"
ms.assetid: 8b55c792-5654-4669-bb0e-a52100f4cabe
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __pin
**참고** 이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [pin\_ptr \(C\+\+\/CLI\)](/visual-cpp/windows/pin-ptr-cpp-cli) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 가비지 컬렉션을 수행하는 동안 관리되는 클래스의 개체 또는 포함 개체가 공용 언어 런타임에 의해 이동하지 않도록 합니다.  
  
## 구문  
  
```  
  
__pin   
identifier  
  
```  
  
## 설명  
 `__pin` 키워드는 개체 또는 관리되는 클래스의 포함 개체에 대한 포인터를 선언하고 가비지 수집 중에 공용 언어 런타임에 의해 개체가 이동하지 않도록 합니다. 관리되지 않는 함수 호출을 확인하는 동안 관리되는 클래스의 주소가 예기치 않게 변경되지 않으므로 주소를 관리되지 않는 함수로 전달할 때 유용합니다.  
  
 고정 포인터는 어휘 범위에서 유효합니다. 고정 포인터가 범위를 벗어나면 개체는 더 이상 고정된 것으로 간주되지 않습니다\(물론 개체를 가리키는 다른 고정 포인터가 없는 경우\).  
  
 MSIL에 "블록 범위" 개념이 없으며 모든 지역 변수는 함수 범위에 있습니다. 고정이 더 이상 유효하지 않다는 것을 시스템에 알리기 위해 컴파일러가 NULL을 고정 포인터에 할당하는 코드를 생성합니다. 블록을 벗어나지 않고 개체를 고정 해제해야 할 경우 직접 이 작업을 할 수도 있습니다.  
  
 고정 포인터를 관리되지 않는 포인터로 변환해서는 안 되며, 고정 포인터가 범위를 벗어나 개체가 더 이상 고정되지 않을 경우 이 관리되지 않는 포인터를 계속 사용하면 안 됩니다. gc 포인터와 달리 고정 포인터는 관리되지 않는 nogc 포인터로 변환할 수 있습니다. 그러나 관리되지 않는 포인터를 사용하는 동안 고정을 유지하는 것은 사용자의 책임입니다.  
  
 고정된 포인터를 사용하여 변수의 주소를 가져와 고정 포인터가 범위를 벗어난 후 이 주소를 사용하면 안 됩니다.  
  
```  
// keyword_pin_scope_bad.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc struct X {  
   int x;  
};  
  
int* Get_x( X* pX ) {  
   int __pin* px = &pX -> x;  
   return px;   // BE CAREFUL px goes of scope,   
                // so object pointed by it is no longer pinned,  
                // making the return value unsafe.  
}  
```  
  
 다음 샘플에서는 올바른 동작을 보여 줍니다.  
  
```  
// keyword_pin_scope_good.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc struct X {  
   int x;  
};  
  
int Get_x( X* pX ) {  
   int __pin* px = &pX -> x;  
   return *px;   // OK, value obtained from px before px out of scope  
}  
```  
  
## 예제  
 다음 예제에서는 범위를 벗어날 때까지 `pG`가 가리키는 개체가 고정됩니다.  
  
```  
// keyword__pin.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
#include <iostream>  
  
__gc class G {   
public:   
   int i;   
   G() {i = 0;};  
};  
  
class H {  
public:  
   // unmanaged function  
   void incr(int * i) {  
      (*i)++;   
      std::cout << *i << std::endl;  
   };  
};  
  
int main() {  
   G __pin * pG = new G;  // pG is a pinning pointer  
   H * h = new H;  
   // pointer to managed data passed as actual parameter of unmanaged   
   // function call  
   h->incr(& pG -> i);   
}  
```  
  
## 출력  
  
```  
1  
```