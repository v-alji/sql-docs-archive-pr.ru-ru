---
title: Соединение с базой данных-источником Oracle | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fccba3d11adc67b3f5ef4f8648ec5d0de07a5648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735521"
---
# <a name="connect-to-an-oracle-source-database"></a><span data-ttu-id="e24db-102">Соединение с базой данных-источником Oracle</span><span class="sxs-lookup"><span data-stu-id="e24db-102">Connect to an Oracle Source Database</span></span>
  <span data-ttu-id="e24db-103">На странице «Источник Oracle» указываются сведения, необходимые для соединения с базой данных-источником Oracle.</span><span class="sxs-lookup"><span data-stu-id="e24db-103">Use the Oracle Source page to provide the information necessary to connect to the Oracle source database.</span></span> <span data-ttu-id="e24db-104">Экземпляр CDC считывает журналы повторов базы данных Oracle, с которой установлено соединение.</span><span class="sxs-lookup"><span data-stu-id="e24db-104">The CDC instance will read the redo logs of the Oracle database you are connected to.</span></span>  
  
 <span data-ttu-id="e24db-105">**Строка подключения Oracle**</span><span class="sxs-lookup"><span data-stu-id="e24db-105">**Oracle Connect String**</span></span>  
 <span data-ttu-id="e24db-106">Введите строку подключения Oracle для компьютера, на котором установлена используемая база данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="e24db-106">Enter the Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="e24db-107">Строка подключения указывается одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="e24db-107">The connect string is written in one of the following ways:</span></span>  
  
 `host[:port][/service name]`  
  
 <span data-ttu-id="e24db-108">В строке подключения также можно указать дескриптор соединения Oracle Net, например `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span><span class="sxs-lookup"><span data-stu-id="e24db-108">The connection string can also specify an Oracle Net connect descriptor, for example, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span></span>  
  
 <span data-ttu-id="e24db-109">Если используется сервер каталогов или файл tnsname, то строкой подключения может быть имя соединения.</span><span class="sxs-lookup"><span data-stu-id="e24db-109">If using a directory server or tnsnames, the connect string can be the name of the connection.</span></span>  
  
 <span data-ttu-id="e24db-110">**Проверка подлинности интеллектуального анализа журналов Oracle**</span><span class="sxs-lookup"><span data-stu-id="e24db-110">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="e24db-111">Чтобы ввести учетные данные проверки подлинности для пользователя базы данных Oracle, который имеет право выполнять интеллектуальный анализ журналов, выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="e24db-111">To enter the credentials for the Oracle database user that is authorized for log mining, select one of the following:</span></span>  
  
-   <span data-ttu-id="e24db-112">**Проверка подлинности Windows**. Выберите этот параметр, чтобы использовать учетные данные текущего пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="e24db-112">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="e24db-113">Этот параметр можно использовать только в том случае, если в базе данных Oracle настроено использование проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="e24db-113">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="e24db-114">**Проверка подлинности Oracle**. При выборе этого варианта необходимо ввести **Имя пользователя** и **Пароль** пользователя в базе данных Oracle, с которой устанавливается соединение.</span><span class="sxs-lookup"><span data-stu-id="e24db-114">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e24db-115">Для выполнения интеллектуального анализа журналов пользователь должен иметь следующие права доступа, предоставленные в базе данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="e24db-115">A user must have the following privileges granted in the Oracle database to be a log-mining user.</span></span>  
> 
>  -   <span data-ttu-id="e24db-116">SELECT на \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="e24db-116">SELECT on \<any-captured-table></span></span>  
> -   <span data-ttu-id="e24db-117">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="e24db-117">SELECT ANY TRANSACTION</span></span>  
> -   <span data-ttu-id="e24db-118">EXECUTE на DBMS LOGMNR</span><span class="sxs-lookup"><span data-stu-id="e24db-118">EXECUTE on DBMS LOGMNR</span></span>  
> -   <span data-ttu-id="e24db-119">SELECT на V$LOGMNR CONTENTS</span><span class="sxs-lookup"><span data-stu-id="e24db-119">SELECT on V$LOGMNR CONTENTS</span></span>  
> -   <span data-ttu-id="e24db-120">SELECT на V$ARCHIVED LOG</span><span class="sxs-lookup"><span data-stu-id="e24db-120">SELECT on V$ARCHIVED LOG</span></span>  
> -   <span data-ttu-id="e24db-121">SELECT на V$LOG</span><span class="sxs-lookup"><span data-stu-id="e24db-121">SELECT on V$LOG</span></span>  
> -   <span data-ttu-id="e24db-122">SELECT на V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="e24db-122">SELECT on V$LOGFILE</span></span>  
> -   <span data-ttu-id="e24db-123">SELECT на V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="e24db-123">SELECT on V$DATABASE</span></span>  
> -   <span data-ttu-id="e24db-124">SELECT на V$THREAD</span><span class="sxs-lookup"><span data-stu-id="e24db-124">SELECT on V$THREAD</span></span>  
> -   <span data-ttu-id="e24db-125">SELECT на ALL INDEXES</span><span class="sxs-lookup"><span data-stu-id="e24db-125">SELECT on ALL INDEXES</span></span>  
> -   <span data-ttu-id="e24db-126">SELECT на ALL OBJECTS</span><span class="sxs-lookup"><span data-stu-id="e24db-126">SELECT on ALL OBJECTS</span></span>  
> -   <span data-ttu-id="e24db-127">SELECT на DBA OBJECTS</span><span class="sxs-lookup"><span data-stu-id="e24db-127">SELECT on DBA OBJECTS</span></span>  
> -   <span data-ttu-id="e24db-128">SELECT на ALL TABLES</span><span class="sxs-lookup"><span data-stu-id="e24db-128">SELECT on ALL TABLES</span></span>  
> 
>  <span data-ttu-id="e24db-129">Если какое-либо из этих прав доступа нельзя предоставить V$xxx, предоставьте его V_S$xxx.</span><span class="sxs-lookup"><span data-stu-id="e24db-129">If any of these privileges cannot be granted to a V$xxx, then grant them to the V_S$xxx.</span></span>  
  
 <span data-ttu-id="e24db-130">**Проверка соединения**</span><span class="sxs-lookup"><span data-stu-id="e24db-130">**Test Connection**</span></span>  
 <span data-ttu-id="e24db-131">Нажмите кнопку **Проверить соединение** , чтобы определить возможность соединения с удаленным компьютером, на котором находится база данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="e24db-131">Click **Test Connection** to determine whether you established a connection with the remote computer that has the Oracle database.</span></span> <span data-ttu-id="e24db-132">Откроется диалоговое окно, в котором будет указано, удалось ли установить соединение.</span><span class="sxs-lookup"><span data-stu-id="e24db-132">A dialog box opens to inform you whether the connection was successful.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e24db-133">Из-за известной проблемы соединение с базой данных-источником Oracle может быть не установлено, если конструктор CDC был запущен не от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="e24db-133">Due to a known issue connection to the Oracle source database may fail if the CDC Designer is not run as an administrator.</span></span> <span data-ttu-id="e24db-134">Если установить соединение не удается, закройте и перезапустите конструктор CDC через пункт меню **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="e24db-134">If connection fails, close and restart the CDC Designer using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="e24db-135">Завершив ввод данных на этой странице, нажмите кнопку **Далее** , чтобы перейти на страницу [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span><span class="sxs-lookup"><span data-stu-id="e24db-135">After you finish entering information on this page, click **Next** to [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e24db-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="e24db-136">See Also</span></span>  
 <span data-ttu-id="e24db-137">[Как создать экземпляр изменения базы данных SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="e24db-137">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="e24db-138">Изменение свойств экземпляра</span><span class="sxs-lookup"><span data-stu-id="e24db-138">Edit Instance Properties</span></span>](edit-instance-properties.md)  
  
  
