---
title: Предложение Skip While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: a3c0749560d8cea1e46d96298347ce54f0bf9185
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863378"
---
# <a name="skip-while-clause-visual-basic"></a>Предложение Skip While (Visual Basic)
Пропускает элементы в коллекции, если заданное условие имеет значение `true`, и возвращает остальные элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательно. Выражение, которое представляет условие для проверки элементов. Выражение должно возвращать `Boolean` значение или функциональный эквивалент, например `Integer` для оценки в качестве `Boolean`.|  
  
## <a name="remarks"></a>Примечания  
 `Skip While` Предложение пропускает элементы в начале результатов запроса до предоставленного `expression` возвращает `false`. После `expression` возвращает `false`, запрос возвращает все оставшиеся элементы. `expression` Игнорируется для оставшихся результатов.  
  
 `Skip While` Предложение отличается от `Where` предложение, в который `Where` предложение может использоваться для исключения всех элементов из запроса, который не удовлетворяют определенному условию. `Skip While` Предложение исключает элементы только до момента первого, условие не выполняется. `Skip While` Предложение наиболее полезно при работе с упорядоченным результатом запроса.  
  
 Можно пропустить определенное количество результатов в начале результата запроса с помощью `Skip` предложение.  
  
## <a name="example"></a>Пример  
 В следующем примере кода используется `Skip While` предложение для обхода результатов, пока не будет найдено первого заказчика из США.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Запросы](../../../visual-basic/language-reference/queries/index.md)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложение Skip](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Предложение Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Предложения Where](../../../visual-basic/language-reference/queries/where-clause.md)
