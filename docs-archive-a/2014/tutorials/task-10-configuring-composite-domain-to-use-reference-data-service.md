---
title: Задача 10. Настройка составного домена для использования службы ссылочных данных | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 752eefde-8b87-4f54-878e-9963ccbadc8e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d70966b4cde110540bf5008eda4e3151fe32f28d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751604"
---
# <a name="task-10-configuring-composite-domain-to-use-reference-data-service"></a><span data-ttu-id="68a7a-102">Задача 10. Настройка составного домена для использования службы эталонных данных</span><span class="sxs-lookup"><span data-stu-id="68a7a-102">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>
  <span data-ttu-id="68a7a-103">В этой задаче вы настраиваете составной домен **проверки адресов** для использования службы **проверки адресов Melissa Data-Address** .</span><span class="sxs-lookup"><span data-stu-id="68a7a-103">In this task, you configure the **Address Validation** composite domain to use the **Melissa Data - Address Check** service.</span></span> <span data-ttu-id="68a7a-104">Во время выполнения при проведении очистки данных службы DQS передают значения доменов в домен проверки адреса, чтобы служба выполнила очистку данных.</span><span class="sxs-lookup"><span data-stu-id="68a7a-104">At runtime, during cleansing activity, DQS passes the values of domains in the Address Validation domain to the service for cleansing.</span></span> <span data-ttu-id="68a7a-105">Дополнительные сведения см. [в статье преобразование домена или составного домена в справочные данные](https://msdn.microsoft.com/library/hh213030.aspx) .</span><span class="sxs-lookup"><span data-stu-id="68a7a-105">See [Map Domain/Composite Domain to Reference Data](https://msdn.microsoft.com/library/hh213030.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="68a7a-106">На главной странице **клиента DQS**в разделе **последние базы знаний** щелкните **поставщики (Управление доменами)** , чтобы открыть страницу **Управление доменами** .</span><span class="sxs-lookup"><span data-stu-id="68a7a-106">In the main page of **DQS Client**, click **Suppliers (Domain Management)** under **Recent Knowledge Bases** to launch the **Domain Management** page.</span></span>  
  
2.  <span data-ttu-id="68a7a-107">Выберите составной домен **Проверка адреса** в **списке доменов**.</span><span class="sxs-lookup"><span data-stu-id="68a7a-107">Select the **Address Validation** composite domain in the **list of domains**.</span></span>  
  
3.  <span data-ttu-id="68a7a-108">На панели справа перейдите на вкладку **Ссылочные данные** .</span><span class="sxs-lookup"><span data-stu-id="68a7a-108">In the right pane, switch to the **Reference Data** tab.</span></span>  
  
     <span data-ttu-id="68a7a-109">![Вкладка эталонных данных](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Вкладка эталонных данных")</span><span class="sxs-lookup"><span data-stu-id="68a7a-109">![Reference Data Tab](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Reference Data Tab")</span></span>  
  
4.  <span data-ttu-id="68a7a-110">Нажмите кнопку **Обзор** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="68a7a-110">Click **Browse** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="68a7a-111">В диалоговом окне **Каталог поставщиков ссылочных данных в сети** установите **флажок** рядом с параметром **Melissa Data-Address Check**.</span><span class="sxs-lookup"><span data-stu-id="68a7a-111">On the **Online Reference Data Providers Catalog** dialog box, select **check box** next to **Melissa Data - Address Check**.</span></span>  
  
     <span data-ttu-id="68a7a-112">![Выбрать Melissa Data — проверка адреса](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Выбрать Melissa Data — проверка адреса")</span><span class="sxs-lookup"><span data-stu-id="68a7a-112">![Select Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Select Melissa Data - Address Check")</span></span>  
  
6.  <span data-ttu-id="68a7a-113">В области справа в разделе **схема** сопоставьте **строку адреса** домен с элементом схемы **адресной строки (M)** с помощью раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="68a7a-113">In the right pane, in the **Schema** section, map **Address Line** domain to the **Address Line (M)** schema item by using the drop-down list.</span></span>  
  
     <span data-ttu-id="68a7a-114">![Сопоставление элемента схемы RDS с доменом](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Сопоставление элемента схемы RDS с доменом")</span><span class="sxs-lookup"><span data-stu-id="68a7a-114">![Map RDS Schema Item to Domain](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Map RDS Schema Item to Domain")</span></span>  
  
7.  <span data-ttu-id="68a7a-115">Нажмите кнопку **Добавить запись схемы (+)** на панели инструментов, чтобы создать запись в списке.</span><span class="sxs-lookup"><span data-stu-id="68a7a-115">Click **Add Schema Entry (+)** button on the toolbar to create an entry in the list.</span></span>  
  
     <span data-ttu-id="68a7a-116">![Кнопка панели инструментов «Добавить элемент схемы»](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Кнопка панели инструментов «Добавить элемент схемы»")</span><span class="sxs-lookup"><span data-stu-id="68a7a-116">![Add Schema Entry Toolbar Button](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Add Schema Entry Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="68a7a-117">Сопоставьте следующие домены DQS с помощью раскрывающегося списка, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="68a7a-117">Map the following DQS domains by using the drop-down lists as shown in the following picture.</span></span>  
  
     <span data-ttu-id="68a7a-118">![Сопоставление элементов схемы RDS с доменами](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Сопоставление элементов схемы RDS с доменами")</span><span class="sxs-lookup"><span data-stu-id="68a7a-118">![Map RDS Schema Items to Domains](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Map RDS Schema Items to Domains")</span></span>  
  
9. <span data-ttu-id="68a7a-119">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="68a7a-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="68a7a-120">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="68a7a-120">Next Step</span></span>  
 [<span data-ttu-id="68a7a-121">Задача 11. Публикация базы знаний</span><span class="sxs-lookup"><span data-stu-id="68a7a-121">Task 11: Publishing the Knowledge Base</span></span>](../../2014/tutorials/task-11-publishing-the-knowledge-base.md)  
  
  
