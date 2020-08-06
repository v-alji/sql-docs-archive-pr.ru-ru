---
title: Создание скрипта таблицы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ea88d736-849e-4368-b55d-06aeee097bf3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 247c839d83768756c57297d47f952401a1c8fd46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658013"
---
# <a name="script-a-table"></a><span data-ttu-id="016ac-102">Создание скрипта таблицы</span><span class="sxs-lookup"><span data-stu-id="016ac-102">Script a Table</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="016ac-103">можно создавать скрипты выбора, вставки, обновления и удаления таблиц, а также скрипты создания, изменения, удаления и выполнения хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="016ac-103">can create scripts to select, insert, update, and delete tables, and to create, alter, drop, or execute stored procedures.</span></span>  
  
 <span data-ttu-id="016ac-104">Иногда возникает необходимость создать скрипт с несколькими действиями, например: удаление процедуры с последующим созданием другой процедуры, создание таблицы и ее изменение.</span><span class="sxs-lookup"><span data-stu-id="016ac-104">Sometimes you want a script with multiple options, such as drop a procedure and then create a procedure, or create a table then alter a table.</span></span> <span data-ttu-id="016ac-105">Чтобы создать комбинированный скрипт, сохраните первый скрипт в окне редактора запросов, а второй — в буфере обмена, чтобы можно было вставить его из буфера обмена в это окно после первого скрипта.</span><span class="sxs-lookup"><span data-stu-id="016ac-105">To create combined scripts, save the first script to a Query Editor window and the second to the clipboard so you can paste it into the window after the first script.</span></span>  
  
## <a name="creating-an-update-script"></a><span data-ttu-id="016ac-106">Создание скрипта обновления</span><span class="sxs-lookup"><span data-stu-id="016ac-106">Creating an Update Script</span></span>  
  
#### <a name="to-create-the-insert-script-for-a-table"></a><span data-ttu-id="016ac-107">Создание скрипта вставки для таблицы</span><span class="sxs-lookup"><span data-stu-id="016ac-107">To create the insert script for a table</span></span>  
  
1.  <span data-ttu-id="016ac-108">В обозревателе объектов разверните узел сервера, последовательно разверните узлы **Базы данных**, [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]и **Таблицы**, щелкните правой кнопкой мыши элемент **HumanResources.Employee**и наведите указатель на пункт **Создать скрипт для таблицы**.</span><span class="sxs-lookup"><span data-stu-id="016ac-108">In Object Explorer, expand your server, expand **Databases**, expand [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], expand **Tables**, right-click **HumanResources.Employee**, and then point to **Script Table As**.</span></span>  
  
2.  <span data-ttu-id="016ac-109">Контекстное меню содержит семь вариантов скрипта: **Использую CREATE**, **Использую DROP**, **Использую DROP и CREATE**, **Использую SELECT**, **Использую INSERT**, **Использую UPDATE**и **Использую DELETE**.</span><span class="sxs-lookup"><span data-stu-id="016ac-109">The shortcut menu has seven available scripting options: **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**, and **DELETE To**.</span></span> <span data-ttu-id="016ac-110">Наведите указатель мыши на вариант **Использую UPDATE**, а затем выберите команду **В новом окне редактора запросов**.</span><span class="sxs-lookup"><span data-stu-id="016ac-110">Point to **UPDATE To**, and then click **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="016ac-111">Откроется новое окно редактора запросов, где будет установлено соединение и полностью отображена инструкция UPDATE.</span><span class="sxs-lookup"><span data-stu-id="016ac-111">A new Query Editor window opens, makes a connection, and presents the entire update statement.</span></span>  
  
     <span data-ttu-id="016ac-112">Это упражнение демонстрирует, что возможность создания скриптов полезна не только для описания в скрипте создания таблицы или хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="016ac-112">This exercise demonstrates how the scripting feature can do more than just script the creation of a table or stored procedure.</span></span> <span data-ttu-id="016ac-113">Новая возможность помогает быстро добавлять скрипты управления данными и легко описывать в скриптах выполнение хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="016ac-113">This new feature can help you quickly add data manipulation scripts to your project and easily script execution of stored procedures.</span></span> <span data-ttu-id="016ac-114">Это позволит сэкономить немало времени при работе с таблицами и хранимыми процедурами, имеющими много полей.</span><span class="sxs-lookup"><span data-stu-id="016ac-114">This can be a big timesaver for tables and procedures with many fields.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="016ac-115">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="016ac-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="016ac-116">Сводка. Создание инструкций на языке Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="016ac-116">Summary: Writing Transact-SQL</span></span>](../../tutorials/summary-writing-transact-sql.md)  
  
  
