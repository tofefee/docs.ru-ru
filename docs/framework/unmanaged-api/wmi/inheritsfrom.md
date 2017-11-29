---
title: "Функция раскрывшемся списке (Справочник по неуправляемым API)"
description: "Функция раскрывшемся списке определяет, является ли класс или экземпляр является производным от определенного родительского класса."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: InheritsFrom
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: InheritsFrom
helpviewer_keywords: InheritsFrom function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aedeec76f4fabb2f6bd32d7d06eb5a1a5734534e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="5ad40-103">Функция раскрывшемся списке</span><span class="sxs-lookup"><span data-stu-id="5ad40-103">InheritsFrom function</span></span>
<span data-ttu-id="5ad40-104">Определяет, является ли текущего класса или экземпляра является производным от класса-родителя указанного.</span><span class="sxs-lookup"><span data-stu-id="5ad40-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5ad40-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ad40-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="5ad40-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ad40-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5ad40-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="5ad40-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5ad40-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5ad40-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="5ad40-109">[in] Имя класса.</span><span class="sxs-lookup"><span data-stu-id="5ad40-109">[in] The name of the class.</span></span> <span data-ttu-id="5ad40-110">`wszAncestor`должен указывать на допустимый `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="5ad40-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5ad40-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5ad40-111">Return value</span></span>

<span data-ttu-id="5ad40-112">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="5ad40-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5ad40-113">Константа</span><span class="sxs-lookup"><span data-stu-id="5ad40-113">Constant</span></span>  |<span data-ttu-id="5ad40-114">Значение</span><span class="sxs-lookup"><span data-stu-id="5ad40-114">Value</span></span>  |<span data-ttu-id="5ad40-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5ad40-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5ad40-116">0</span><span class="sxs-lookup"><span data-stu-id="5ad40-116">0</span></span> | <span data-ttu-id="5ad40-117">Наследует текущий объект `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="5ad40-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="5ad40-118">1</span><span class="sxs-lookup"><span data-stu-id="5ad40-118">1</span></span> | <span data-ttu-id="5ad40-119">Текущий объект не является производным от `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="5ad40-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5ad40-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5ad40-120">0x80041008</span></span> | <span data-ttu-id="5ad40-121">Свойство `wszAncestor` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="5ad40-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="5ad40-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ad40-122">Remarks</span></span>

<span data-ttu-id="5ad40-123">Эта функция создает оболочку для вызова [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="5ad40-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5ad40-124">Требования</span><span class="sxs-lookup"><span data-stu-id="5ad40-124">Requirements</span></span>  
 <span data-ttu-id="5ad40-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ad40-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad40-126">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5ad40-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5ad40-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5ad40-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad40-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5ad40-128">See also</span></span>  
[<span data-ttu-id="5ad40-129">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5ad40-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)