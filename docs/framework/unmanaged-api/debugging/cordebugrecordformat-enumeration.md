---
title: "Перечисление CorDebugRecordFormat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRecordFormat
api_location: mscordbi.dll
api_type: COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c2f8397382dde061078a0d96114420f1c5f48669
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="3ef4f-102">Перечисление CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="3ef4f-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="3ef4f-103">Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.</span><span class="sxs-lookup"><span data-stu-id="3ef4f-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ef4f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="3ef4f-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3ef4f-105">Members</span></span>  
  
|<span data-ttu-id="3ef4f-106">Член</span><span class="sxs-lookup"><span data-stu-id="3ef4f-106">Member</span></span>|<span data-ttu-id="3ef4f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3ef4f-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="3ef4f-108">Данные представляют собой 32-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="3ef4f-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="3ef4f-109">Данные представляют собой 64-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="3ef4f-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ef4f-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ef4f-110">Remarks</span></span>  
 <span data-ttu-id="3ef4f-111">Член `CorDebugRecordFormat` передается перечисление [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод для указания формата массива байтов в его `pRecord` аргумент.</span><span class="sxs-lookup"><span data-stu-id="3ef4f-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ef4f-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3ef4f-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ef4f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3ef4f-113">Requirements</span></span>  
 <span data-ttu-id="3ef4f-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ef4f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ef4f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ef4f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ef4f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ef4f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ef4f-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ef4f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef4f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3ef4f-118">See Also</span></span>  
 [<span data-ttu-id="3ef4f-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="3ef4f-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)