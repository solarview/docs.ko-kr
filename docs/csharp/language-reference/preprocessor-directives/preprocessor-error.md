---
title: '#error - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: b335dfeed23d43938c66f0753590af55ac99b12a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235597"
---
# <a name="error-c-reference"></a>#error(C# 참조)
`#error`를 사용하면 코드의 특정 위치에서 [CS1029](../compiler-messages/cs1029.md) 사용자 정의 오류를 생성할 수 있습니다. 예:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>설명  
 `#error`은 일반적으로 조건부 지시문에 사용됩니다.  
  
 [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.  
  
## <a name="example"></a>예제  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)  
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [C# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)
