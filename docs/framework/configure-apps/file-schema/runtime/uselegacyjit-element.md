---
title: "&lt;useLegacyJit&gt; элемент"
ms.custom: 
ms.date: 04/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 735733fc33a21c2f275c1ea9894c43558f01626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltuselegacyjitgt-element"></a><span data-ttu-id="73d33-102">&lt;useLegacyJit&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="73d33-102">&lt;useLegacyJit&gt; Element</span></span>

<span data-ttu-id="73d33-103">Определяет, использует ли среда CLR устаревший 64-разрядный JIT-компилятор для JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="73d33-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="73d33-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73d33-104">\<configuration></span></span>  
<span data-ttu-id="73d33-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="73d33-105">\<runtime></span></span>  
<span data-ttu-id="73d33-106">\<useLegacyJit ></span><span class="sxs-lookup"><span data-stu-id="73d33-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="73d33-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73d33-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="73d33-108">Имя элемента `useLegacyJit` учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="73d33-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73d33-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="73d33-109">Attributes and elements</span></span>

<span data-ttu-id="73d33-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="73d33-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73d33-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="73d33-111">Attributes</span></span>  
  
| <span data-ttu-id="73d33-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="73d33-112">Attribute</span></span> | <span data-ttu-id="73d33-113">Описание</span><span class="sxs-lookup"><span data-stu-id="73d33-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="73d33-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="73d33-114">Required attribute.</span></span><br><br><span data-ttu-id="73d33-115">Указывает, использует ли среда выполнения устаревших 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="73d33-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="73d33-116">атрибут Enabled</span><span class="sxs-lookup"><span data-stu-id="73d33-116">enabled attribute</span></span>  
  
| <span data-ttu-id="73d33-117">Значение</span><span class="sxs-lookup"><span data-stu-id="73d33-117">Value</span></span> | <span data-ttu-id="73d33-118">Описание</span><span class="sxs-lookup"><span data-stu-id="73d33-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="73d33-119">0</span><span class="sxs-lookup"><span data-stu-id="73d33-119">0</span></span>     | <span data-ttu-id="73d33-120">Общеязыковая среда выполнения использует новый 64-разрядных JIT-компилятор, включенные в .NET Framework 4.6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="73d33-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="73d33-121">1</span><span class="sxs-lookup"><span data-stu-id="73d33-121">1</span></span>     | <span data-ttu-id="73d33-122">Общеязыковая среда выполнения использует старую 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="73d33-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="73d33-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="73d33-123">Child elements</span></span>

<span data-ttu-id="73d33-124">Нет</span><span class="sxs-lookup"><span data-stu-id="73d33-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="73d33-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="73d33-125">Parent elements</span></span>  
  
| <span data-ttu-id="73d33-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="73d33-126">Element</span></span>         | <span data-ttu-id="73d33-127">Описание</span><span class="sxs-lookup"><span data-stu-id="73d33-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="73d33-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73d33-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="73d33-129">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="73d33-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="73d33-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="73d33-130">Remarks</span></span>  

<span data-ttu-id="73d33-131">Начиная с .NET Framework 4.6, общеязыковая среда выполнения использует новый 64-разрядный компилятор JIT – JIT-компиляции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="73d33-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="73d33-132">В некоторых случаях это может привести различие в поведении из кода приложения, который был скомпилирован JIT предыдущей версии 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="73d33-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="73d33-133">Установив `enabled` атрибут `<useLegacyJit>` элемент `1`, можно отключить новый 64-разрядный компилятор JIT и вместо этого компиляции приложения с помощью прежних версий 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="73d33-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73d33-134">`<useLegacyJit>` Элемента влияет на 64-разрядного JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="73d33-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="73d33-135">Компиляция с 32-разрядный компилятор JIT не влияет.</span><span class="sxs-lookup"><span data-stu-id="73d33-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="73d33-136">Вместо того чтобы использовать параметр файла конфигурации, можно включить устаревший 64-разрядный компилятор JIT двумя способами:</span><span class="sxs-lookup"><span data-stu-id="73d33-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="73d33-137">Задание переменной среды</span><span class="sxs-lookup"><span data-stu-id="73d33-137">Setting an environment variable</span></span>

  <span data-ttu-id="73d33-138">Задать `COMPLUS_useLegacyJit` переменной среды, либо `0` (используйте новый 64-разрядный компилятор JIT) или `1` (использовать старые 64-разрядный компилятор JIT):</span><span class="sxs-lookup"><span data-stu-id="73d33-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="73d33-139">Переменная среды содержит *глобальной области*, что означает, что он влияет на все приложения выполняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="73d33-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="73d33-140">Если задано, оно может быть переопределено параметр файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="73d33-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="73d33-141">Имя переменной среды не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="73d33-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="73d33-142">Добавление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="73d33-142">Adding a registry key</span></span>

  <span data-ttu-id="73d33-143">Прежних версий 64-разрядный компилятор JIT можно включить, добавив `REG_DWORD` значение либо `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` или `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` ключа в реестре.</span><span class="sxs-lookup"><span data-stu-id="73d33-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="73d33-144">Значение называется `useLegacyJit`.</span><span class="sxs-lookup"><span data-stu-id="73d33-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="73d33-145">Если значение равно 0, используется новый компилятор.</span><span class="sxs-lookup"><span data-stu-id="73d33-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="73d33-146">Если значение равно 1, устаревших 64-разрядный компилятор JIT включен.</span><span class="sxs-lookup"><span data-stu-id="73d33-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="73d33-147">Имя значения реестра не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="73d33-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="73d33-148">Добавление значения в `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` ключ затрагивает все приложения, запущенного на компьютере.</span><span class="sxs-lookup"><span data-stu-id="73d33-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="73d33-149">Добавление значения в `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` ключ затрагивает все приложения, выполнить от текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="73d33-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="73d33-150">Если компьютер настроен с несколькими учетными записями, затрагиваются только приложений, выполните для текущего пользователя, если только значение добавляется к разделам реестра для других пользователей, а также.</span><span class="sxs-lookup"><span data-stu-id="73d33-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="73d33-151">Добавление `<useLegacyJit>` в файле конфигурации переопределяет параметры реестра, если они присутствуют.</span><span class="sxs-lookup"><span data-stu-id="73d33-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73d33-152">Пример</span><span class="sxs-lookup"><span data-stu-id="73d33-152">Example</span></span>  

<span data-ttu-id="73d33-153">В следующем файле конфигурации отключает компиляцию с помощью нового 64-разрядный компилятор JIT и вместо этого использует устаревших 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="73d33-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73d33-154">См. также</span><span class="sxs-lookup"><span data-stu-id="73d33-154">See also</span></span>

<span data-ttu-id="73d33-155">[\<Среда выполнения > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="73d33-155">[\<runtime> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) </span></span>  
<span data-ttu-id="73d33-156">[\<Конфигурация > элемент](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="73d33-156">[\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
[<span data-ttu-id="73d33-157">Устранение рисков. Новый 64-разрядный JIT-компилятор</span><span class="sxs-lookup"><span data-stu-id="73d33-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)