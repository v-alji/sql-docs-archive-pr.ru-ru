---
title: Изменение свойств базы данных Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraProp
ms.assetid: 58dc99f1-ee6b-4508-bb66-2bc589611ff7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3cad2735e6cd6095f9730f3b4e7228526451d34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657851"
---
# <a name="edit-the-oracle-database-properties"></a><span data-ttu-id="da35a-102">Изменение свойств базы данных Oracle</span><span class="sxs-lookup"><span data-stu-id="da35a-102">Edit the Oracle Database Properties</span></span>
  <span data-ttu-id="da35a-103">На вкладке Oracle в редакторе свойств можно изменить описание, которое было введено на странице создания базы данных CDC мастера создания экземпляра, а также изменить данные для подключения к базе данных интеллектуального анализа журналов Oracle.</span><span class="sxs-lookup"><span data-stu-id="da35a-103">Use the Oracle tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
 <span data-ttu-id="da35a-104">Ниже описаны данные, отображаемые на вкладке **Oracle** .</span><span class="sxs-lookup"><span data-stu-id="da35a-104">The following describes the information in the **Oracle** tab.</span></span>  
  
 <span data-ttu-id="da35a-105">**Название**</span><span class="sxs-lookup"><span data-stu-id="da35a-105">**Name**</span></span>  
 <span data-ttu-id="da35a-106">Имя экземпляра CDC, введенное на странице создания базы данных CDC в мастере создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="da35a-106">The name of the CDC Instance that you entered in the Create CDC Database page in the New Instance wizard.</span></span> <span data-ttu-id="da35a-107">Это поле доступно только для чтения, отображаемые в нем данные нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="da35a-107">This field is read only and you cannot edit this information.</span></span>  
  
 <span data-ttu-id="da35a-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="da35a-108">**Description**</span></span>  
 <span data-ttu-id="da35a-109">Можно изменить описание нового экземпляра или добавить его, если оно не было введено при создании экземпляра CDC.</span><span class="sxs-lookup"><span data-stu-id="da35a-109">You can edit the description of the new instance or add one if you did not do so when creating the CDC Instance.</span></span>  
  
 <span data-ttu-id="da35a-110">**Строка подключения Oracle**</span><span class="sxs-lookup"><span data-stu-id="da35a-110">**Oracle Connect String**</span></span>  
 <span data-ttu-id="da35a-111">Строка подключения Oracle для компьютера, на котором находится используемая база данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="da35a-111">The Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="da35a-112">Это поле доступно только для чтения, отображаемые в нем данные нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="da35a-112">This field is read only and you cannot edit this information.</span></span> <span data-ttu-id="da35a-113">Причина этого заключается в том, что при внесении изменений в строку подключения экземпляр Oracle CDC может быть направлен к совершенно другой базе данных Oracle, что приведет к повреждению состояния экземпляра CDC, хранящегося в таблице **cdc.xdbcdc_config** .</span><span class="sxs-lookup"><span data-stu-id="da35a-113">This is because some changes to the connect string may point the Oracle CDC Instance to another Oracle database entirely, corrupting the CDC Instance state as stored in the **cdc.xdbcdc_config** table.</span></span> <span data-ttu-id="da35a-114">Если в строку подключения необходимо внести незначительные изменения, то сделать это можно непосредственно в таблице конфигурации с помощью среды SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="da35a-114">If minor changes are needed, you can change the connect string directly in the configuration table using SQL Server Management Studio.</span></span>  
  
 <span data-ttu-id="da35a-115">**Проверка подлинности интеллектуального анализа журналов Oracle**</span><span class="sxs-lookup"><span data-stu-id="da35a-115">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="da35a-116">Чтобы ввести учетные данные проверки подлинности для базы данных Oracle, в которой находится средство интеллектуального анализа журналов, выберите в разделе **Проверка подлинности**один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="da35a-116">To enter the authentication credentials for the Oracle database that contains the log miner, select one of the following under **Authentication**:</span></span>  
  
-   <span data-ttu-id="da35a-117">**Проверка подлинности Windows**. Выберите этот параметр, чтобы использовать учетные данные текущего пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="da35a-117">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="da35a-118">Этот параметр можно использовать только в том случае, если в базе данных Oracle настроено использование проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="da35a-118">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="da35a-119">**Проверка подлинности Oracle**. При выборе этого варианта необходимо ввести **Имя пользователя** и **Пароль** пользователя в базе данных Oracle, с которой устанавливается соединение.</span><span class="sxs-lookup"><span data-stu-id="da35a-119">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
 <span data-ttu-id="da35a-120">Свойства базы данных Oracle можно просмотреть в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="da35a-120">You can view the Oracle database properties in the viewer.</span></span> <span data-ttu-id="da35a-121">При использовании средства просмотра отображаемые в нем данные доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="da35a-121">When using the viewer the information is read only.</span></span> <span data-ttu-id="da35a-122">В средстве просмотра отображается также список отслеживаемых столбцов из таблицы.</span><span class="sxs-lookup"><span data-stu-id="da35a-122">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="da35a-123">Дополнительные сведения о доступе к средству просмотра см. в разделе [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="da35a-123">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da35a-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="da35a-124">See Also</span></span>  
 <span data-ttu-id="da35a-125">[Как управлять службой CDC из консоли конструктора CDC](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="da35a-125">[How to Manage a CDC Service from the CDC Designer Console](how-to-manage-a-cdc-service-from-the-cdc-designer-console.md) </span></span>  
 <span data-ttu-id="da35a-126">[Соединение с базой данных-источником Oracle](connect-to-an-oracle-source-database.md) </span><span class="sxs-lookup"><span data-stu-id="da35a-126">[Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md) </span></span>  
 [<span data-ttu-id="da35a-127">Соединение с Oracle</span><span class="sxs-lookup"><span data-stu-id="da35a-127">Connect to Oracle</span></span>](connect-to-oracle.md)  
  
  
