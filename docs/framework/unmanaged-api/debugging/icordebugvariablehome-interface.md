---
title: "Интерфейс ICorDebugVariableHome"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea8f4033a6b0878288c49d6f6d964eb40675162d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehome-interface"></a><span data-ttu-id="96be2-102">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="96be2-102">ICorDebugVariableHome Interface</span></span>
<span data-ttu-id="96be2-103">Представляет локальную переменную или аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="96be2-103">Represents a local variable or argument of a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96be2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="96be2-104">Methods</span></span>  
  
|<span data-ttu-id="96be2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="96be2-105">Method</span></span>|<span data-ttu-id="96be2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="96be2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96be2-107">Метод GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="96be2-107">GetArgumentIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|<span data-ttu-id="96be2-108">Возвращает индекс аргумента функции.</span><span class="sxs-lookup"><span data-stu-id="96be2-108">Gets the index of a function argument.</span></span>|  
|[<span data-ttu-id="96be2-109">Метод GetCode</span><span class="sxs-lookup"><span data-stu-id="96be2-109">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|<span data-ttu-id="96be2-110">Возвращает экземпляр «ICorDebugCode», содержащий это `ICorDebugVariableHome` объекта.</span><span class="sxs-lookup"><span data-stu-id="96be2-110">Gets the "ICorDebugCode" instance that contains this `ICorDebugVariableHome` object.</span></span>|  
|[<span data-ttu-id="96be2-111">Метод GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="96be2-111">GetLiveRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|<span data-ttu-id="96be2-112">Получает собственный диапазон, по которому эта переменная является динамической.</span><span class="sxs-lookup"><span data-stu-id="96be2-112">Gets the native range over which this variable is live.</span></span>|  
|[<span data-ttu-id="96be2-113">Метод GetLocationType</span><span class="sxs-lookup"><span data-stu-id="96be2-113">GetLocationType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|<span data-ttu-id="96be2-114">Возвращает тип собственного расположение переменной.</span><span class="sxs-lookup"><span data-stu-id="96be2-114">Gets the type of the variable's native location.</span></span>|  
|[<span data-ttu-id="96be2-115">GetOffset-метод</span><span class="sxs-lookup"><span data-stu-id="96be2-115">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|<span data-ttu-id="96be2-116">Получает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="96be2-116">Gets the offset from the base register for a variable.</span></span>|  
|[<span data-ttu-id="96be2-117">Метод GetRegister</span><span class="sxs-lookup"><span data-stu-id="96be2-117">GetRegister Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|<span data-ttu-id="96be2-118">Возвращает регистра, который содержит переменную с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="96be2-118">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>|  
|[<span data-ttu-id="96be2-119">Метод GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="96be2-119">GetSlotIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|<span data-ttu-id="96be2-120">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="96be2-120">Gets the managed slot-index of a local variable.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="96be2-121">Пример</span><span class="sxs-lookup"><span data-stu-id="96be2-121">Example</span></span>  
 <span data-ttu-id="96be2-122">В следующем фрагменте кода используется [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) объект с именем `pCode4`.</span><span class="sxs-lookup"><span data-stu-id="96be2-122">The following code fragment uses the [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) object named `pCode4`.</span></span>  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="96be2-123">Требования</span><span class="sxs-lookup"><span data-stu-id="96be2-123">Requirements</span></span>  
 <span data-ttu-id="96be2-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96be2-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96be2-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96be2-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96be2-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96be2-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96be2-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96be2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96be2-128">См. также</span><span class="sxs-lookup"><span data-stu-id="96be2-128">See Also</span></span>  
 [<span data-ttu-id="96be2-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="96be2-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="96be2-130">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="96be2-130">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)