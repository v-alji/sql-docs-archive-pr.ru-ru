---
title: Настройка общих свойств отчета (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], properties
- properties [Reporting Services], general
ms.assetid: 10b941b2-28e6-4408-9ee4-acebc63c8496
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f30900158591afcd5997053dbb61cc22b495ed10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739554"
---
# <a name="configure-general-properties-for-a-report-report-manager"></a><span data-ttu-id="25f96-102">Настройка общих свойств отчета (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="25f96-102">Configure General Properties for a Report (Report Manager)</span></span>
  
### <a name="to-configure-general-report-properties"></a><span data-ttu-id="25f96-103">Настройка общих свойств отчета</span><span class="sxs-lookup"><span data-stu-id="25f96-103">To configure general report properties</span></span>

1.  <span data-ttu-id="25f96-104">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="25f96-104">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>

2.  <span data-ttu-id="25f96-105">В диспетчер отчетов перейдите на страницу **содержимое** .</span><span class="sxs-lookup"><span data-stu-id="25f96-105">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="25f96-106">Перейдите к отчету, для которого нужно настроить конфигурацию общих свойств, и откройте его.</span><span class="sxs-lookup"><span data-stu-id="25f96-106">Navigate to the report that you want to configure general properties for and open it.</span></span>

3.  <span data-ttu-id="25f96-107">Щелкните вкладку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="25f96-107">Click the **Properties** tab.</span></span>

     <span data-ttu-id="25f96-108">Или, если страница **содержимое** находится в представлении Details, щелкните значок страницы свойств:</span><span class="sxs-lookup"><span data-stu-id="25f96-108">Or, if the **Contents** page is in Details view, click the property page icon:</span></span>

     <span data-ttu-id="25f96-109">![Значок страницы свойств](media/prop.gif "Значок страницы свойств")</span><span class="sxs-lookup"><span data-stu-id="25f96-109">![Property page icon](media/prop.gif "Property page icon")</span></span>

4.  <span data-ttu-id="25f96-110">Отобразится страница **Общие** свойства, и можно настроить свойства следующим образом.</span><span class="sxs-lookup"><span data-stu-id="25f96-110">The **General** properties page is displayed, and you can configure properties as follows:</span></span>

    -   <span data-ttu-id="25f96-111">В разделе **Свойства** можно изменить имя и описание отчета.</span><span class="sxs-lookup"><span data-stu-id="25f96-111">In the **Properties** section, you can modify the report name and description.</span></span>

    -   <span data-ttu-id="25f96-112">Можно установить флажок **Скрыть в представлении списка** , чтобы скрыть элемент при открытии страницы в макете страницы по умолчанию (представление списка), где элементы упорядочиваются по странице.</span><span class="sxs-lookup"><span data-stu-id="25f96-112">You can select the **Hide in list view** checkbox to hide the item when the page is opened in the default page layout (list view) which arranges items across and down the page.</span></span>

    -   <span data-ttu-id="25f96-113">В разделе **Определение отчета** нажмите кнопку **изменить** , чтобы извлечь копию определения отчета.</span><span class="sxs-lookup"><span data-stu-id="25f96-113">In the **Report Definition** section, click **Edit** to extract a copy of the report definition.</span></span> <span data-ttu-id="25f96-114">Изменения определения отчетов, произведенные локально, на сервере отчетов не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="25f96-114">Modifications that you make locally to the report definition are not saved on the report server.</span></span>

         <span data-ttu-id="25f96-115">Или, чтобы обновить определение отчета из RDL-файла, нажмите кнопку **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="25f96-115">Or, to update the report definition from an .rdl file, click **Update**.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="25f96-116">По завершении обновления определения отчета необходимо сбросить параметры настроек источника данных.</span><span class="sxs-lookup"><span data-stu-id="25f96-116">If you update a report definition, you must reset the data source settings after the update is completed.</span></span>

    -   <span data-ttu-id="25f96-117">Используйте кнопки **Удалить** или **переместить** , чтобы удалить или переместить отчет.</span><span class="sxs-lookup"><span data-stu-id="25f96-117">Use the **Delete** or **Move** buttons to delete or move the report.</span></span>

    -   <span data-ttu-id="25f96-118">Можно также создать связанный отчет.</span><span class="sxs-lookup"><span data-stu-id="25f96-118">You can also create a linked report.</span></span>

5.  <span data-ttu-id="25f96-119">Завершив настройку общих свойств отчета, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="25f96-119">When you have finished configuring general properties for the report, click **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="25f96-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="25f96-120">See Also</span></span>
 <span data-ttu-id="25f96-121">[Перемещение или удаление элемента &#40;диспетчер отчетов](report-server/move-or-delete-an-item-report-manager.md) [Страница "содержимое"&#41;&#40;диспетчер отчетов](../../2014/reporting-services/contents-page-report-manager.md) [Поиск, просмотр и управление отчетами&#41;&#40;и службы SSRS построитель отчетов](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [страница "Общие свойства", отчеты &#41;&#40;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) диспетчер отчетов</span><span class="sxs-lookup"><span data-stu-id="25f96-121">[Move or Delete an Item &#40;Report Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)</span></span>


