---
title: Создание домена | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createdomain.f1
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fad6abd795aa9412bb71d251623d92d3e13b889c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655982"
---
# <a name="create-a-domain"></a><span data-ttu-id="44fd3-102">Создание домена</span><span class="sxs-lookup"><span data-stu-id="44fd3-102">Create a Domain</span></span>
  <span data-ttu-id="44fd3-103">В этом разделе описывается, как создать домен в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="44fd3-103">This topic describes how to create a domain in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="44fd3-104">Значения в домене являются семантическим представлением данных в поле.</span><span class="sxs-lookup"><span data-stu-id="44fd3-104">The values in the domain are a semantic representation of the data in a field.</span></span> <span data-ttu-id="44fd3-105">Дополнительные сведения о доменах см. в разделе [Управление доменом](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="44fd3-105">For more information on domains, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
 <span data-ttu-id="44fd3-106">Существуют следующие два способа создания нового домена.</span><span class="sxs-lookup"><span data-stu-id="44fd3-106">There are two ways to create a new domain.</span></span> <span data-ttu-id="44fd3-107">Первый — на этапе сопоставления действий по обнаружению знаний, в процессе анализа образца данных для добавления набора знаний в новую или существующую базу знаний.</span><span class="sxs-lookup"><span data-stu-id="44fd3-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="44fd3-108">Второй — в ходе действий по управлению доменами, когда вместо изменения существующего домена вы создаете новый.</span><span class="sxs-lookup"><span data-stu-id="44fd3-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44fd3-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="44fd3-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="44fd3-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="44fd3-110">Prerequisites</span></span>  
 <span data-ttu-id="44fd3-111">Чтобы создать домен, необходимо создать и открыть базу знаний.</span><span class="sxs-lookup"><span data-stu-id="44fd3-111">To create a domain, you must have created and opened a knowledge base.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44fd3-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="44fd3-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44fd3-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="44fd3-113">Permissions</span></span>  
 <span data-ttu-id="44fd3-114">Для создания домена необходимо иметь в базе данных DQS_MAIN роль dqs_administrator или dqs_kb_editor.</span><span class="sxs-lookup"><span data-stu-id="44fd3-114">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to create a domain.</span></span>  
  
##  <a name="create-a-domain-in-the-knowledge-discovery-activity"></a><a name="Discovery"></a> <span data-ttu-id="44fd3-115">Создание домена в ходе операции обнаружения знаний</span><span class="sxs-lookup"><span data-stu-id="44fd3-115">Create a Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="44fd3-116">[Запустите приложение Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="44fd3-116">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="44fd3-117">На главной странице [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Открыть базу знаний** и выберите базу знаний или нажмите кнопку **Создать базу знаний** и введите свойства новой базы знаний.</span><span class="sxs-lookup"><span data-stu-id="44fd3-117">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="44fd3-118">Выберите действие **Обнаружение знаний** и нажмите кнопку **Создать** , чтобы создать новую базу знаний, или нажмите кнопку **Открыть** , чтобы открыть существующую базу знаний.</span><span class="sxs-lookup"><span data-stu-id="44fd3-118">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="44fd3-119">На странице **Сопоставление** укажите соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="44fd3-119">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="44fd3-120">Дополнительные сведения см. в разделе [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="44fd3-120">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="44fd3-121">В таблице **Сопоставления** выберите исходный столбец из раскрывающегося списка для столбца **Исходный столбец** пустой строки.</span><span class="sxs-lookup"><span data-stu-id="44fd3-121">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="44fd3-122">Если соответствующий домен не существует, щелкните значок **Создать домен** .</span><span class="sxs-lookup"><span data-stu-id="44fd3-122">If no corresponding domain exists, click the **Create a Domain** icon.</span></span>  
  
##  <a name="create-a-domain-in-the-domain-management-activity"></a><a name="DomainManagement"></a><span data-ttu-id="44fd3-123">Создание домена в действии "Управление доменами"</span><span class="sxs-lookup"><span data-stu-id="44fd3-123">Create a Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="44fd3-124">На главной странице [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] нажмите кнопку **Открыть базу знаний** и выберите базу знаний или нажмите кнопку **Создать базу знаний** и введите свойства новой базы знаний.</span><span class="sxs-lookup"><span data-stu-id="44fd3-124">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="44fd3-125">Выберите действие **Управление доменами** и нажмите кнопку **Создать** , чтобы создать новую базу знаний, или нажмите кнопку **Открыть** , чтобы открыть существующую базу знаний.</span><span class="sxs-lookup"><span data-stu-id="44fd3-125">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="44fd3-126">На странице **Управление доменами** щелкните значок **Создать домен** над списком доменов.</span><span class="sxs-lookup"><span data-stu-id="44fd3-126">On the **Domain Management** page, click the **Create a Domain** icon above the Domain list.</span></span>  
  
##  <a name="set-domain-properties"></a><a name="Properties"></a><span data-ttu-id="44fd3-127">Задание свойств домена</span><span class="sxs-lookup"><span data-stu-id="44fd3-127">Set Domain Properties</span></span>  
  
1.  <span data-ttu-id="44fd3-128">В диалоговом окне **Создание домена** введите имя, уникальное в базе знаний, и описание длиной не более 256 символов.</span><span class="sxs-lookup"><span data-stu-id="44fd3-128">In the **Create Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="44fd3-129"> Дополнительные сведения о свойствах домена см. в разделе [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span><span class="sxs-lookup"><span data-stu-id="44fd3-129">For more information about domain properties, see [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span></span>  
  
2.  <span data-ttu-id="44fd3-130">Из списка **Тип данных** выберите тип данных для значений в домене.</span><span class="sxs-lookup"><span data-stu-id="44fd3-130">From the **Data Type** list, select a data type for the values in the domain.</span></span> <span data-ttu-id="44fd3-131">Типом данных может быть **String** (по умолчанию), **Date**, **Integer**или **Decimal**.</span><span class="sxs-lookup"><span data-stu-id="44fd3-131">The data type can be **String** (the default), **Date**, **Integer**, or **Decimal**.</span></span>  
  
3.  <span data-ttu-id="44fd3-132">Выберите **Использовать ведущие значения** , чтобы указать, что будет выдано ведущее значение в группе синонимов, а не значение, которое является его синонимом.</span><span class="sxs-lookup"><span data-stu-id="44fd3-132">Select **Use Leading Values** to specify that the leading value in a group of synonyms will be output instead of a value that is a synonym to it.</span></span> <span data-ttu-id="44fd3-133">Снимите флажок **Использовать ведущие значения** , чтобы указать, что каждое значение синонима выводится в правильной или исправленной форме, и не заменяется ведущим значением для группы.</span><span class="sxs-lookup"><span data-stu-id="44fd3-133">Deselect **Use Leading Values** to specify that each synonym value is output in its correct or corrected form, and is not replaced by the leading value for its group.</span></span>  
  
4.  <span data-ttu-id="44fd3-134">Если тип данных — **String**, выберите **Нормализовать строку** , чтобы удалить специальные символы в значениях домена, что может увеличить вероятность совпадений.</span><span class="sxs-lookup"><span data-stu-id="44fd3-134">If the data type is **String**, select **Normalize String** to remove special characters in the domain values, which may improve the likelihood of matches.</span></span>  
  
5.  <span data-ttu-id="44fd3-135">Из раскрывающегося списка **Формат вывода** выберите формат, который будет применяться при выводе значений данных домена.</span><span class="sxs-lookup"><span data-stu-id="44fd3-135">From the **Format Output to** drop-down list, select the formatting that will be applied when the data values in the domain are output.</span></span> <span data-ttu-id="44fd3-136">Форматирование зависит от типа данных, выбранного в шаге 2, как показано в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="44fd3-136">The formatting is specific to the data type selected in step 2, as shown in the following list:</span></span>  
  
    -   <span data-ttu-id="44fd3-137">Для строкового значения вы можете указать, что строка выводится в верхнем регистре, нижнем регистре или прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="44fd3-137">For a string value, you can specify that the string be output as upper case, lower case, or capitalized.</span></span>  
  
    -   <span data-ttu-id="44fd3-138">Для значения даты вы можете указать формат дня, месяца и года.</span><span class="sxs-lookup"><span data-stu-id="44fd3-138">For a date value, you can specify the format of the day, month, and year.</span></span>  
  
    -   <span data-ttu-id="44fd3-139">Для целочисленного значения вы можете указать тип маски формата, которую следует применить.</span><span class="sxs-lookup"><span data-stu-id="44fd3-139">For an integer value, you can specify the type of format mask to be applied.</span></span>  
  
    -   <span data-ttu-id="44fd3-140">Для десятичного значения вы можете указать точность и тип маски формата, которую следует применить.</span><span class="sxs-lookup"><span data-stu-id="44fd3-140">For a decimal value, you can specify the accuracy and the type of format mask to be applied.</span></span>  
  
     <span data-ttu-id="44fd3-141">Если выбрать **Нет** в раскрывающемся списке **Формат вывода@@@** , ни один из форматов в списке не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="44fd3-141">Selecting **None** in the **Format Output to** drop-down list means none of the formats in the list will be applied.</span></span>  
  
6.  <span data-ttu-id="44fd3-142">Если тип данных — **String**, из раскрывающегося списка **Язык** выберите язык варианта проверки орфографии, который необходимо применить в случае, если проверка орфографии включена.</span><span class="sxs-lookup"><span data-stu-id="44fd3-142">If the data type is **String**, in the **Language** drop-down list, select which language version of the speller you want to apply if you enable the speller.</span></span>  
  
7.  <span data-ttu-id="44fd3-143">Если тип данных — **String**, выберите **Включить проверку орфографии** , чтобы применять проверку орфографии ко всем строковым значениям при заполнении домена.</span><span class="sxs-lookup"><span data-stu-id="44fd3-143">If the data type is **String**, select **Enable Speller** to run the Speller on all string values when populating the domain.</span></span>  
  
8.  <span data-ttu-id="44fd3-144">Если тип данных — **String**, выберите **Отключить алгоритмы поиска ошибок синтаксиса** , чтобы заполнить домен без поиска синтаксических ошибок в строковых значениях.</span><span class="sxs-lookup"><span data-stu-id="44fd3-144">If the data type is **String**, select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span>  
  
9. <span data-ttu-id="44fd3-145">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="44fd3-145">Click **OK**.</span></span>  
  
10. <span data-ttu-id="44fd3-146">Нажмите кнопку **Готово** , чтобы завершить операцию управления доменами, как описано в разделе [Завершение операции по управлению доменами](../../2014/data-quality-services/end-the-domain-management-activity.md).</span><span class="sxs-lookup"><span data-stu-id="44fd3-146">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="44fd3-147">Дальнейшие действия. После создания правила домена</span><span class="sxs-lookup"><span data-stu-id="44fd3-147">Follow Up: After Creating a Domain</span></span>  
 <span data-ttu-id="44fd3-148">Создав домен, вы можете выполнить другие задачи управления доменами для этого домена, провести обнаружение знаний для добавления знаний в домен или добавить в домен политику сопоставления.</span><span class="sxs-lookup"><span data-stu-id="44fd3-148">After you create a domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="44fd3-149">Дополнительные сведения см. в разделах [Обнаружение набора знаний](../../2014/data-quality-services/perform-knowledge-discovery.md), [Управление доменом](../../2014/data-quality-services/managing-a-domain.md) и [Создание политики сопоставления](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="44fd3-149">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
