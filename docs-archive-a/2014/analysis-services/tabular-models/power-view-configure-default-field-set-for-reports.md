---
title: Настройка набора полей по умолчанию для отчетов Power View (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66fbbacd0cc2efd7d379bcc8e68149551476869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728793"
---
# <a name="configure-default-field-set-for-power-view-reports-ssas-tabular"></a><span data-ttu-id="a76da-102">Настройка набора полей по умолчанию для отчетов Power View (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="a76da-102">Configure Default Field Set for Power View Reports (SSAS Tabular)</span></span>
  <span data-ttu-id="a76da-103">Набор полей по умолчанию представляет собой предустановленный список столбцов и мер, которые автоматически добавляются на лист отчета [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] при выборе таблицы из списка полей отчета.</span><span class="sxs-lookup"><span data-stu-id="a76da-103">A default field set is a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span> <span data-ttu-id="a76da-104">Автор табличной модели может создавать наборы полей по умолчанию, чтобы удалить лишние шаги для создателей отчетов, которые используют модель данных для своих отчетов.</span><span class="sxs-lookup"><span data-stu-id="a76da-104">Tabular model authors can create a default field set to eliminate redundant steps for report authors who use the model for their reports.</span></span> <span data-ttu-id="a76da-105">Например, если известно, что большинство авторов отчетов, работающих с контактными сведениями клиентов, хотят видеть имя, основной номер телефона, адрес электронной почты и название компании, можно сделать предварительный выбор этих столбцов так, чтобы они всегда добавлялись на лист отчета, если автор щелкает таблицу «Сведения о клиентах».</span><span class="sxs-lookup"><span data-stu-id="a76da-105">For example, if you know that most report authors who work with customer contact information always want to see a contact name, a primary phone number, an email address, and a company name, you can pre-select those columns so that they are always added to the report canvas when the author clicks the Customer Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a76da-106">Набор полей по умолчанию применим только к табличной модели, которая используется в качестве модели данных в [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a76da-106">A default field set applies only to a tabular model used as a data model in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="a76da-107">Наборы полей по умолчанию не поддерживаются в сводных отчетах Excel.</span><span class="sxs-lookup"><span data-stu-id="a76da-107">Default field sets are not supported in Excel pivot reports.</span></span>  
  
## <a name="creating-a-default-field-set"></a><span data-ttu-id="a76da-108">Создание набора полей по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a76da-108">Creating a Default Field Set</span></span>  
 <span data-ttu-id="a76da-109">Пользователь определяет, какие поля должны быть включены по умолчанию при выборе любой таблицы в [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a76da-109">You can determine which fields, if any, are included by default whenever a specific table is selected in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="a76da-110">Владелец книги также может определять порядок появления полей в списке.</span><span class="sxs-lookup"><span data-stu-id="a76da-110">You can also determine the order in which fields appear in the list.</span></span> <span data-ttu-id="a76da-111">Чтобы указать набор полей по умолчанию, необходимо задать свойства отчета в проекте табличной модели.</span><span class="sxs-lookup"><span data-stu-id="a76da-111">To specify a default field set, you set report properties in the tabular model project.</span></span>  
  
#### <a name="to-add-a-default-field-set"></a><span data-ttu-id="a76da-112">Добавление набора полей по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a76da-112">To add a default field set</span></span>  
  
1.  <span data-ttu-id="a76da-113">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]щелкните таблицу (вкладку), для которой настраивается список полей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a76da-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the table (tab) for which you are configuring a default field list.</span></span>  
  
2.  <span data-ttu-id="a76da-114">В окне **Свойства** щелкните в поле **Набор полей по умолчанию** и выберите команду **Щелкнуть для изменения**.</span><span class="sxs-lookup"><span data-stu-id="a76da-114">In the **Properties** window, in the **Default Field Set** property, click **Click to edit**.</span></span>  
  
3.  <span data-ttu-id="a76da-115">В диалоговом окне «Набор полей по умолчанию» выберите одно или несколько полей.</span><span class="sxs-lookup"><span data-stu-id="a76da-115">In the Default Field Set dialog, select one or more fields.</span></span> <span data-ttu-id="a76da-116">Можно выбрать любое поле из таблицы, включая меры.</span><span class="sxs-lookup"><span data-stu-id="a76da-116">You can choose any field in the table, including measures.</span></span> <span data-ttu-id="a76da-117">Удерживайте клавишу SHIFT, чтобы выбрать диапазон, или клавишу CTRL, чтобы выбрать определенные ячейки.</span><span class="sxs-lookup"><span data-stu-id="a76da-117">Hold down the Shift key to select a range, or the Ctrl key to select individual fields.</span></span>  
  
4.  <span data-ttu-id="a76da-118">Нажмите кнопку **Добавить** , чтобы добавить их в набор полей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a76da-118">Click **Add** to add them to the default field set.</span></span>  
  
5.  <span data-ttu-id="a76da-119">С помощью кнопок «Вниз» и «Вверх» задайте порядок полей в списке.</span><span class="sxs-lookup"><span data-stu-id="a76da-119">Use the Up and Down buttons to specify an order to the field list.</span></span> <span data-ttu-id="a76da-120">Поля будут добавлены в отчет в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="a76da-120">Fields will be added to the report in the order defined for the field set.</span></span>  
  
6.  <span data-ttu-id="a76da-121">Повторите шаги для других таблиц книги.</span><span class="sxs-lookup"><span data-stu-id="a76da-121">Repeat these steps for other tables in your workbook.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a76da-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="a76da-122">Next Step</span></span>  
 <span data-ttu-id="a76da-123">После создания набора полей по умолчанию можно также указать заголовки по умолчанию, изображения, групповые поведения или указать, должны строки, содержащие одно значение, группироваться вместе в одну строку или отображаться по отдельности.</span><span class="sxs-lookup"><span data-stu-id="a76da-123">After you create a default field set, you can further influence the report design experience by specifying default labels, default images, default group behavior, or whether rows that contain the same value are grouped together in one row or listed individually.</span></span> <span data-ttu-id="a76da-124">Дополнительные сведения см. в разделе [Настройка свойств работы таблицы для отчетов Power View (табличные службы SSAS)](power-view-configure-table-behavior-properties-for-reports.md).</span><span class="sxs-lookup"><span data-stu-id="a76da-124">For more information, see [Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span></span>  
  
  
