---
title: 배열에 foreach 사용 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: a290cd709dd6491981658f467fa0163011290128
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238470"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>배열에 foreach 사용(C# 프로그래밍 가이드)

[foreach](../../language-reference/keywords/foreach-in.md) 문은 배열의 요소를 반복하는 단순하고 깔끔한 방법을 제공합니다.

1차원 배열의 경우 `foreach` 문은 인덱스 0으로 시작하고 인덱스 `Length - 1`로 끝나는 늘어나는 인덱스 순서로 요소를 처리합니다.

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

다차원 배열의 경우 요소는 가장 오른쪽 차원의 인덱스가 먼저 증가한 이후, 다음 왼쪽 차원의 인덱스, 그다음 왼쪽 차원의 인덱스가 증가하는 방식으로 트래버스됩니다.

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

그러나 다차원 배열에서 중첩 [for](../../language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 처리하는 순서를 더 강력하게 제어할 수 있습니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Array>  
- [C# 프로그래밍 가이드](../index.md)  
- [배열](index.md)  
- [1차원 배열](single-dimensional-arrays.md)  
- [다차원 배열](multidimensional-arrays.md)  
- [가변 배열](jagged-arrays.md)
