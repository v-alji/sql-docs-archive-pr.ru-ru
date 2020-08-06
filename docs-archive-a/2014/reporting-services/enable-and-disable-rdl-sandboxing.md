---
title: Включение и отключение "песочница" для языка определения отчетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d5619e9f-ec5b-4376-9b34-1f74de6fade7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7af1477751093862c99d00978278315e600511e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735054"
---
# <a name="enable-and-disable-rdl-sandboxing"></a><span data-ttu-id="fc0f5-102">Включение и отключение «песочницы» для языка определения отчетов</span><span class="sxs-lookup"><span data-stu-id="fc0f5-102">Enable and Disable RDL Sandboxing</span></span>
  <span data-ttu-id="fc0f5-103">Функция «песочницы» для языка определения отчетов позволяет обнаруживать и ограничивать использование определенных типов ресурсов отдельными пользователями в среде с многочисленными пользователями, которые используют единственную веб-ферму серверов отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-103">The RDL (Report Definition Language) Sandboxing feature lets you detect and restrict the usage of specific types of resources, by individual tenants, in an environment of multiple tenants that use a single web farm of report servers.</span></span> <span data-ttu-id="fc0f5-104">Примером этого является сценарий услуг хост-сервера, в котором может поддерживаться единственная веб-ферма серверов отчетов, применяемая несколькими пользователями, а также, возможно, другими компаниями.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-104">An example of this is a hosting services scenario where you might maintain a single web farm of report servers that are used by multiple tenants, and perhaps different companies.</span></span> <span data-ttu-id="fc0f5-105">Администратор сервера отчетов может включить эту функцию для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-105">As a report server administrator, you can enable this feature to help achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="fc0f5-106">Ограничение размера внешних ресурсов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-106">Restrict external resource sizes.</span></span> <span data-ttu-id="fc0f5-107">Внешние ресурсы включают изображения, XSLT-файлы и данные карт.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-107">External resources include images, .xslt files, and map data.</span></span>  
  
-   <span data-ttu-id="fc0f5-108">Во время публикации отчета ограничить типы и члены, используемые в тексте выражения.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-108">At report publish time, limit types and members that are used in expression text.</span></span>  
  
-   <span data-ttu-id="fc0f5-109">Во время выполнения ограничить длину текста и размер возвращаемых значений для выражений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-109">At report processing time, limit the length of the text and the size of the return value for expressions.</span></span>  
  
 <span data-ttu-id="fc0f5-110">При включении функции «песочницы» для языка определения отчетов отключаются следующие функции:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-110">When RDL Sandboxing is enabled, the following features are disabled:</span></span>  
  
-   <span data-ttu-id="fc0f5-111">Пользовательский код в **\<Code>** элементе определения отчета.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-111">Custom code in the **\<Code>** element of a report definition.</span></span>  
  
-   <span data-ttu-id="fc0f5-112">режим обратной совместимости выражений языка определения отчетов для пользовательских элементов отчета [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-112">RDL backward compatibility mode for [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] custom report items.</span></span>  
  
-   <span data-ttu-id="fc0f5-113">именованные параметры в выражениях.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-113">Named parameters in expressions.</span></span>  
  
 <span data-ttu-id="fc0f5-114">В этом разделе описывается каждый элемент в `RDLSandboxing` элементе <> в RSReportServer.Configном файле.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-114">This topic describes each element in the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span> <span data-ttu-id="fc0f5-115">Дополнительные сведения об изменении файла см. в разделе [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="fc0f5-115">For more information about how to modify this file, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="fc0f5-116">Операции с записями журнала трассировки сервера, связанные с функцией «песочницы» для выражений языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-116">A server trace log records activity related to the RDL Sandboxing feature.</span></span> <span data-ttu-id="fc0f5-117">Дополнительные сведения о журналах трассировки см. в разделе [Журнал трассировки службы сервера отчетов](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="fc0f5-117">For more information about trace logs, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="fc0f5-118">Пример конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc0f5-118">Example Configuration</span></span>  
 <span data-ttu-id="fc0f5-119">В следующем примере показаны параметры и примеры значений для `RDLSandboxing` элемента <> в RSReportServer.Configном файле.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-119">The following example shows the settings and example values for the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span>  
  
```  
<RDLSandboxing>  
   <MaxExpressionLength>5000</MaxExpressionLength>  
   <MaxResourceSize>5000</MaxResourceSize>  
   <MaxStringResultLength>3000</MaxStringResultLength>  
   <MaxArrayResultLength>250</MaxArrayResultLength>  
   <Types>  
      <Allow Namespace="System.Drawing" AllowNew="True">Bitmap</Allow>  
      <Allow Namespace="TypeConverters.Custom" AllowNew="True">*</Allow>  
   </Types>  
   <Members>  
      <Deny>Format</Deny>  
      <Deny>StrDup</Deny>  
   </Members>  
</RDLSandboxing>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="fc0f5-120">Параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc0f5-120">Configuration Settings</span></span>  
 <span data-ttu-id="fc0f5-121">Сведения о параметрах настройки приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-121">The following table provides information about configuration settings.</span></span> <span data-ttu-id="fc0f5-122">Параметры представлены в том порядке, в котором они следуют в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-122">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="fc0f5-123">Параметр</span><span class="sxs-lookup"><span data-stu-id="fc0f5-123">Setting</span></span>|<span data-ttu-id="fc0f5-124">Описание</span><span class="sxs-lookup"><span data-stu-id="fc0f5-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc0f5-125">**MaxExpressionLength**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-125">**MaxExpressionLength**</span></span>|<span data-ttu-id="fc0f5-126">Максимально допустимое число символов в выражении языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-126">Maximum number of characters allowed in RDL expressions.</span></span><br /><br /> <span data-ttu-id="fc0f5-127">Значение по умолчанию: 1000</span><span class="sxs-lookup"><span data-stu-id="fc0f5-127">Default: 1000</span></span>|  
|<span data-ttu-id="fc0f5-128">**MaxResourceSize**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-128">**MaxResourceSize**</span></span>|<span data-ttu-id="fc0f5-129">Максимально допустимый размер внешнего ресурса (КБ).</span><span class="sxs-lookup"><span data-stu-id="fc0f5-129">Maximum number of KB allowed for an external resource.</span></span><br /><br /> <span data-ttu-id="fc0f5-130">По умолчанию — 100</span><span class="sxs-lookup"><span data-stu-id="fc0f5-130">Default: 100</span></span>|  
|<span data-ttu-id="fc0f5-131">**MaxStringResultLength**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-131">**MaxStringResultLength**</span></span>|<span data-ttu-id="fc0f5-132">Максимально допустимое число символов для возвращаемого значения выражения языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-132">Maximum number of characters allowed in a return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="fc0f5-133">Значение по умолчанию: 1000</span><span class="sxs-lookup"><span data-stu-id="fc0f5-133">Default: 1000</span></span>|  
|<span data-ttu-id="fc0f5-134">**MaxArrayResultLength**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-134">**MaxArrayResultLength**</span></span>|<span data-ttu-id="fc0f5-135">Максимальное число элементов для возвращаемого значения выражения языка определения отчетов, допустимое в массиве.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-135">Maximum number of items allowed in an array return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="fc0f5-136">По умолчанию — 100</span><span class="sxs-lookup"><span data-stu-id="fc0f5-136">Default: 100</span></span>|  
|<span data-ttu-id="fc0f5-137">**Типы**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-137">**Types**</span></span>|<span data-ttu-id="fc0f5-138">Список членов, разрешенных для выражений языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-138">The list of members to allow within RDL expressions.</span></span>|  
|<span data-ttu-id="fc0f5-139">**Разрешить**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-139">**Allow**</span></span>|<span data-ttu-id="fc0f5-140">Тип или набор типов, разрешенных для выражений языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-140">A type or set of types to allow in RDL expressions.</span></span>|  
|<span data-ttu-id="fc0f5-141">**Пространство имен**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-141">**Namespace**</span></span>|<span data-ttu-id="fc0f5-142">Атрибут для элемента **Allow** , представляющий пространство имен, содержащее один или несколько типов, применимых к атрибуту Value.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-142">Attribute for **Allow** that is the namespace that contains one or more types that apply to Value.</span></span> <span data-ttu-id="fc0f5-143">Это свойство учитывает регистр символов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-143">This property is case-insensitive.</span></span>|  
|`AllowNew`|<span data-ttu-id="fc0f5-144">Логический атрибут для **allow** , определяющий, разрешено ли создание новых экземпляров типа в выражениях языка определения отчетов или в элементе языка определения отчетов **\<Class>** .</span><span class="sxs-lookup"><span data-stu-id="fc0f5-144">Boolean attribute for **Allow** that controls whether new instances of the type are allowed to be created in RDL expressions or in an RDL **\<Class>** element.</span></span><br /><br /> <span data-ttu-id="fc0f5-145">Примечание. Если `RDLSandboxing` включен, новые массивы не могут быть созданы в выражениях языка определения отчетов, независимо от значения параметра `AllowNew` .</span><span class="sxs-lookup"><span data-stu-id="fc0f5-145">Note: When `RDLSandboxing` is enabled, new arrays cannot be created in RDL expressions, regardless of the setting of `AllowNew`.</span></span>|  
|<span data-ttu-id="fc0f5-146">**Значение**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-146">**Value**</span></span>|<span data-ttu-id="fc0f5-147">Значение элемента **Allow** , представляющее имя типа, разрешенного в выражениях языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-147">Value for **Allow** that is the name of the type to allow in RDL expressions.</span></span> <span data-ttu-id="fc0f5-148">Значение **\*** указывает, что разрешены все типы в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-148">The value **\*** indicates that all types in the namespace are allowed.</span></span> <span data-ttu-id="fc0f5-149">Это свойство учитывает регистр символов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-149">This property is case-insensitive.</span></span>|  
|<span data-ttu-id="fc0f5-150">**Члены**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-150">**Members**</span></span>|<span data-ttu-id="fc0f5-151">Для списка типов, включенных в **\<Types>** элемент, список имен членов, недопустимых в выражениях языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-151">For the list of types that are include in the **\<Types>** element, the list of member names that are not allowed in RDL expressions.</span></span>|  
|<span data-ttu-id="fc0f5-152">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="fc0f5-152">**Deny**</span></span>|<span data-ttu-id="fc0f5-153">Имя члена, запрещенного в выражении языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-153">The name of a member that is not allowed in RDL expressions.</span></span> <span data-ttu-id="fc0f5-154">Это свойство учитывает регистр символов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-154">This property is case-insensitive.</span></span><br /><br /> <span data-ttu-id="fc0f5-155">Примечание. Если для элемента указано **Deny** , то все элементы всех типов с этим именем будут запрещены.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-155">Note: When **Deny** is specified for a member, all members with this name for all types are not allowed.</span></span>|  
  
## <a name="working-with-expressions-when-rdl-sandboxing-is-enabled"></a><span data-ttu-id="fc0f5-156">Работа с выражениями в режиме «песочницы» для выражений языка определения отчетов</span><span class="sxs-lookup"><span data-stu-id="fc0f5-156">Working with Expressions when RDL Sandboxing is Enabled</span></span>  
 <span data-ttu-id="fc0f5-157">Функцию «песочницы» для выражений языка определения отчетов можно изменить, чтобы обеспечить управление ресурсами, используемыми в выражении, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-157">You can modify the RDL Sandboxing feature to help manage the resources that are used by an expression in the following ways:</span></span>  
  
-   <span data-ttu-id="fc0f5-158">ограничение количества символов, используемых в выражении;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-158">Restrict the number of characters that are used for an expression.</span></span>  
  
-   <span data-ttu-id="fc0f5-159">ограничение размера результата, возвращаемого выражением;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-159">Restrict the size of the result returned by an expression.</span></span>  
  
-   <span data-ttu-id="fc0f5-160">разрешение списка определенных типов, которые могут быть использованы в выражении;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-160">Allow a specific list of types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="fc0f5-161">ограничение списка членов по именам для списка разрешенных типов, которые могут быть использованы в выражении;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-161">Restrict the list of members by name for the list of allowed types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="fc0f5-162">функция «песочницы» для выражений языка определения отчетов позволяет создать список разрешенных типов и список запрещенных членов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-162">The RDL Sandboxing feature enables you to create a list of approved types and a list of denied members.</span></span> <span data-ttu-id="fc0f5-163">Список разрешенных типов называется списком разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-163">The list of approved types is called an allow list.</span></span> <span data-ttu-id="fc0f5-164">Список запрещенных членов называется списком блокировок.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-164">The list of denied members is called a block list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc0f5-165">В определении отчета компьютеру неизвестны типы всех экземпляров в справочниках выражений служб.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-165">In the report definition, a computer cannot know the type of each instances of an expression reference.</span></span> <span data-ttu-id="fc0f5-166">При добавлении члена к списку блокировок в списке разрешений блокируются все члены всех типов с этим именем.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-166">When you add a member to the block list, you are denying all members of that name across all types in the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-167">Проверка результатов выражений языка определения отчетов производится во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-167">RDL expression results are verified at run time.</span></span> <span data-ttu-id="fc0f5-168">Выражения языка определения отчетов проверяются в определении отчета при публикации отчета.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-168">RDL expressions are verified in the report definition when the report is published.</span></span> <span data-ttu-id="fc0f5-169">Наблюдение за журналом трассировки сервера отчетов на наличие нарушений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-169">Monitor the report server trace log for violations.</span></span> <span data-ttu-id="fc0f5-170">Дополнительные сведения см. в статье [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="fc0f5-170">For more information, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
### <a name="working-with-types"></a><span data-ttu-id="fc0f5-171">Работа с типами</span><span class="sxs-lookup"><span data-stu-id="fc0f5-171">Working with Types</span></span>  
 <span data-ttu-id="fc0f5-172">При добавлении типа к списку разрешений осуществляется управление следующими точками входа, используемыми для доступа к выражениям языка определения отчетов:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-172">When you add a type to the allow list, you are controlling the following entry points to access RDL expressions:</span></span>  
  
-   <span data-ttu-id="fc0f5-173">статические члены этого типа;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-173">Static members of a type.</span></span>  
  
-   <span data-ttu-id="fc0f5-174">[!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` Метод.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-174">The [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` method.</span></span>  
  
-   <span data-ttu-id="fc0f5-175">**\<Classes>** Элемент в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-175">The **\<Classes>** element in the report definition.</span></span>  
  
-   <span data-ttu-id="fc0f5-176">члены, добавленные к списку блокировок, для типа в списке разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-176">Members that you have added to the block list for a type in the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-177">Список разрешений не управляет следующими точками входа:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-177">The allow list does not control the following entry points:</span></span>  
  
-   <span data-ttu-id="fc0f5-178">наборы данных отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-178">Report datasets.</span></span> <span data-ttu-id="fc0f5-179">Поля в наборах данных отчетов, возвращаемые при запросах, могут содержать любой допустимый тип выражения языка определения отчетов;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-179">Fields in report datasets that are returned from queries might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="fc0f5-180">параметры отчета;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-180">Report parameters.</span></span> <span data-ttu-id="fc0f5-181">Указанные пользователем значения параметров могут содержать любой допустимый тип выражения языка определения отчетов;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-181">User-supplied parameter values might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="fc0f5-182">члены разрешенного типа, не состоящие в списке блокировок.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-182">Members of an enabled type that are not in the block list.</span></span> <span data-ttu-id="fc0f5-183">По умолчанию разрешены все члены всех типов в списке разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-183">By default, all members of all types in the allow list are enabled.</span></span> <span data-ttu-id="fc0f5-184">При добавлении имени члена к списку блокировок в списке разрешений блокируются все члены всех типов с этим именем.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-184">When you add a member name to the block list, you are denying all members with that name across all types that are in the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-185">Чтобы разрешить член одного типа и запретить член другого типа с тем же именем, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-185">To enable a member of one type but deny a member with the same name for a different type, you must do the following:</span></span>  
  
-   <span data-ttu-id="fc0f5-186">Добавьте **\<Deny>** элемент для имени члена.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-186">Add a **\<Deny>** element for the member name.</span></span>  
  
-   <span data-ttu-id="fc0f5-187">в пользовательской сборке создать в классе член-посредник с другим именем для того члена, который необходимо разрешить;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-187">Create a proxy member with a different name on a class in a custom assembly for the member that you want to enable.</span></span>  
  
-   <span data-ttu-id="fc0f5-188">добавить этот новый класс к списку разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-188">Add that new class to the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-189">Чтобы добавить функции [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework к списку разрешений, добавьте к списку разрешений соответствующие типы из пространства имен Microsoft.VisualBasic.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-189">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework functions to the allow list, add the corresponding types from the Microsoft.VisualBasic namespace to the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-190">Чтобы добавить ключевые слова, определяющие тип [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework, добавьте к списку разрешений соответствующий тип CLR.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-190">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework type keywords to the allow list, add the corresponding CLR type to the allow list.</span></span> <span data-ttu-id="fc0f5-191">Например, чтобы использовать [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ключевое слово .NET Framework `Integer` , добавьте следующий фрагмент XML в **\<RDLSandboxing>** элемент:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-191">For example, to use the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework keyword `Integer`, add the following XML fragment to the **\<RDLSandboxing>** element:</span></span>  
  
```  
<Allow Namespace="System">Int32</Allow>  
```  
  
 <span data-ttu-id="fc0f5-192">Чтобы добавить универсальный или допускающий значения NULL тип .NET Framework [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] к списку разрешений, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-192">To add a generic or a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type to the allow list, you must do the following:</span></span>  
  
-   <span data-ttu-id="fc0f5-193">создайте тип-посредник для универсального или допускающего значения NULL типа .NET Framework [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-193">Create a proxy type for the generic or [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type.</span></span>  
  
-   <span data-ttu-id="fc0f5-194">добавьте тип-посредник к списку разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-194">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-195">При добавлении типа из пользовательской сборки к списку разрешений для сборки неявное предоставление разрешения на выполнение не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-195">Adding a type from a custom assembly to the allow list does not implicitly grant execute permission on the assembly.</span></span> <span data-ttu-id="fc0f5-196">Необходимо специально изменить файл управления доступом для кода, предоставив разрешение на выполнение для данной сборки.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-196">You must specifically modify the code access security file and provide execute permission to your assembly.</span></span> <span data-ttu-id="fc0f5-197">Дополнительные сведения см. в статье [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fc0f5-197">For more information, see [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
#### <a name="maintaining-the-deny-list-of-members"></a><span data-ttu-id="fc0f5-198">Обслуживание \<Deny> списка членов</span><span class="sxs-lookup"><span data-stu-id="fc0f5-198">Maintaining the \<Deny> List of Members</span></span>  
 <span data-ttu-id="fc0f5-199">В следующем списке показано, когда необходимо обновление списка заблокированных членов при добавлении нового типа к списку разрешений:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-199">When you add a new type to the allow list, use the following list to determine when you might have to update the block list of members:</span></span>  
  
-   <span data-ttu-id="fc0f5-200">при обновлении пользовательской сборки до версии, в которой вводятся новые типы;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-200">When you update a custom assembly with a version that introduces new types.</span></span>  
  
-   <span data-ttu-id="fc0f5-201">при добавлении новых членов к типам в списке разрешений;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-201">When you add members to the types in the allow list.</span></span>  
  
-   <span data-ttu-id="fc0f5-202">при обновлении [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] на сервере отчетов;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-202">When you update the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] on the report server.</span></span>  
  
-   <span data-ttu-id="fc0f5-203">при обновлении сервера отчетов до последней версии служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)];</span><span class="sxs-lookup"><span data-stu-id="fc0f5-203">When you upgrade the report server to a later version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="fc0f5-204">при обновлении сервера отчетов для обработки последней схемы языка определения отчетов при добавлении новых членов к типам языка определения отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-204">When you update a report server to handle a later RDL schema, because new members might have been added to RDL types.</span></span>  
  
### <a name="working-with-operators-and-new"></a><span data-ttu-id="fc0f5-205">Работа с операторами и оператором New</span><span class="sxs-lookup"><span data-stu-id="fc0f5-205">Working with Operators and New</span></span>  
 <span data-ttu-id="fc0f5-206">По умолчанию все операторы языка [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework, кроме `New`, всегда разрешены.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-206">By default, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework language operators, except for `New`, are always allowed.</span></span> <span data-ttu-id="fc0f5-207">`New`Оператор управляется `AllowNew` атрибутом **\<Allow>** элемента.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-207">The `New` operator is controlled by the `AllowNew` attribute on the **\<Allow>** element.</span></span> <span data-ttu-id="fc0f5-208">Всегда разрешены другие операторы языка, такие как оператор метода доступа коллекции по умолчанию `!` и [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Frameworkные макросы приведения `CInt` .</span><span class="sxs-lookup"><span data-stu-id="fc0f5-208">Other language operators, such as the default collection accessor operator `!` and [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework cast macros such as `CInt`, are always allowed.</span></span>  
  
 <span data-ttu-id="fc0f5-209">Добавление операторов к списку заблокированных, включая пользовательские, не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-209">Adding operators to a block list, including custom operators, is not supported.</span></span> <span data-ttu-id="fc0f5-210">Чтобы исключить тип операторов, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-210">To exclude operators for a type, you must do the following:</span></span>  
  
-   <span data-ttu-id="fc0f5-211">создайте тип-посредник, не реализующий операторы, которые необходимо исключить;.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-211">Create a proxy type that does not implement the operators that you want to exclude.</span></span>  
  
-   <span data-ttu-id="fc0f5-212">добавьте тип-посредник к списку разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-212">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-213">Чтобы создать новый массив в выражении языка определения отчетов, создайте массив в определяемом классе и добавьте этот класс к списку разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-213">To create a new array in an RDL expression, create the array in a method on a class that you define, and add that class to the allow list.</span></span>  
  
 <span data-ttu-id="fc0f5-214">Чтобы создать новый массив в выражении языка определения отчетов, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-214">To create a new array in an RDL expression, you must do the following:</span></span>  
  
-   <span data-ttu-id="fc0f5-215">определите новый класс и создайте массив в методе в этом классе;</span><span class="sxs-lookup"><span data-stu-id="fc0f5-215">Define a new class and create the array in a method on that class.</span></span>  
  
-   <span data-ttu-id="fc0f5-216">добавьте этот класс к списку разрешений.</span><span class="sxs-lookup"><span data-stu-id="fc0f5-216">Add the class to the allow list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc0f5-217">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc0f5-217">See Also</span></span>  
 <span data-ttu-id="fc0f5-218">[Файл конфигурации RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="fc0f5-218">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 [<span data-ttu-id="fc0f5-219">Журнал трассировки службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="fc0f5-219">Report Server Service Trace Log</span></span>](report-server/report-server-service-trace-log.md)  
  
  
