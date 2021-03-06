---
title: Выражения объекта (F#)
description: 'Узнайте, как использовать объектов выражений F #, если вы хотите избежать дополнительного кода и затраты, необходимые для создания нового именованного типа.'
ms.date: 05/16/2016
ms.openlocfilehash: 1a971044d680d3bf5a6fff38affdaf001d5403b4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865466"
---
# <a name="object-expressions"></a>Выражения объекта

*Объекта выражение* является выражение, которое создает новый экземпляр динамически создаваемого анонимного типа объекта, который основан на существующем базовом типе, интерфейсе или набор интерфейсов.

## <a name="syntax"></a>Синтаксис

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Примечания

В приведенном выше синтаксисе *typename* представляет собой существующий тип класса или тип интерфейса. *Тип params* описывает необязательные параметры универсального типа. *Аргументы* используются только для типов классов, которые требуют параметры конструктора. *Определения членов* переопределения методов базового класса или реализаций абстрактных методов базового класса или интерфейса.

Следующий пример иллюстрирует несколько разных типов выражений объекта.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>С использованием выражений объекта

Объект выражения используются в том случае, если вы хотите избежать дополнительного кода и издержки, который необходим для создания нового именованного типа. Если объект выражения позволяют свести к минимуму количество типов, созданный в приложении, можно сократить число строк кода и предотвратить ненужное увеличение числа типов. Вместо создания множества типов для различных ситуаций, можно использовать выражение объекта, который настраивает существующий тип или предоставляет подходящую реализацию интерфейса для конкретного случая.

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
