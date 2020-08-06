---
title: Инструкция SQL Create Table (мастер импорта и экспорта SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createtablesql.f1
ms.assetid: 0d6f6b3b-d023-4770-a8a9-65b2977c8d05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3fc2054711708a27691f2d7219c33749f11b977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666157"
---
# <a name="create-table-sql-statement-sql-server-import-and-export-wizard"></a><span data-ttu-id="fa93d-102">Инструкция SQL Create Table (мастер импорта и экспорта SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fa93d-102">Create Table SQL Statement (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="fa93d-103">Используйте диалоговое окно **инструкция SQL CREATE TABLE** , чтобы просмотреть инструкцию, которая была создана автоматически, или изменить ее в целях.</span><span class="sxs-lookup"><span data-stu-id="fa93d-103">Use the **Create Table SQL Statement** dialog box to view the statement that was generated automatically, or to modify it for your purposes.</span></span> <span data-ttu-id="fa93d-104">При изменении этой инструкции можно также сделать соответствующие изменения в сопоставлении столбцов, после чего будет необходимо вручную обрабатывать измененную инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="fa93d-104">If you modify this statement, you may also have to make associated changes to column mapping, and you will have to maintain the edited SQL statement manually thereafter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="fa93d-105">формируют инструкцию по умолчанию CREATE TABLE на основании подключенных источников данных.</span><span class="sxs-lookup"><span data-stu-id="fa93d-105">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="fa93d-106">Эта инструкция CREATE TABLE не включает атрибут FILESTREAM, даже если исходная таблица содержит столбец, для которого объявлен атрибут FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="fa93d-106">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="fa93d-107">Чтобы запустить компонент служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с атрибутом FILESTREAM, сначала следует создать хранилище FILESTREAM в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="fa93d-107">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="fa93d-108">Затем добавьте атрибут FILESTREAM к инструкции CREATE TABLE в диалоговом окне **Создание таблицы** .</span><span class="sxs-lookup"><span data-stu-id="fa93d-108">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="fa93d-109">Дополнительные сведения см. в разделе [Данные большого двоичного объекта (SQL Server)](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fa93d-109">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="fa93d-110">Дополнительные сведения о работе этого мастера см. в разделе [Мастер импорта и экспорта SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa93d-110">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="fa93d-111">Дополнительные сведения о параметрах запуска мастера, а также о разрешениях, необходимых для успешного запуска мастера, см. в разделе [Запуск мастера импорта и экспорта SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa93d-111">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="fa93d-112">Назначение мастера импорта и экспорта SQL Server заключается в копировании данных из исходного расположения в целевое.</span><span class="sxs-lookup"><span data-stu-id="fa93d-112">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="fa93d-113">Этот мастер может также создать целевую базу данных и целевые таблицы.</span><span class="sxs-lookup"><span data-stu-id="fa93d-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="fa93d-114">Однако если нужно скопировать несколько баз данных, таблиц или других объектов базы данных, следует использовать мастер копирования баз данных.</span><span class="sxs-lookup"><span data-stu-id="fa93d-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="fa93d-115">Дополнительные сведения см. в статье [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa93d-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa93d-116">Варианты</span><span class="sxs-lookup"><span data-stu-id="fa93d-116">Options</span></span>  
 <span data-ttu-id="fa93d-117">**Инструкция SQL**</span><span class="sxs-lookup"><span data-stu-id="fa93d-117">**SQL statement**</span></span>  
 <span data-ttu-id="fa93d-118">Выводит автоматически созданную инструкцию SQL и позволяет редактировать ее.</span><span class="sxs-lookup"><span data-stu-id="fa93d-118">Displays the auto-generated SQL statement and lets it be edited.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fa93d-119">Если в конце инструкции SQL необходимо вставить символ возврата каретки, нажмите клавиши CTRL+ВВОД.</span><span class="sxs-lookup"><span data-stu-id="fa93d-119">If you want to include a carriage return in the SQL statement, press CTRL+ENTER.</span></span> <span data-ttu-id="fa93d-120">При нажатии одной лишь клавиши ВВОД диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="fa93d-120">If you press only ENTER, the dialog box closes.</span></span>  
  
 <span data-ttu-id="fa93d-121">**Автоформирование**</span><span class="sxs-lookup"><span data-stu-id="fa93d-121">**Autogenerate**</span></span>  
 <span data-ttu-id="fa93d-122">Если инструкция SQL по умолчанию была изменена, ее можно вернуть к исходному виду, нажав кнопку **Автоформирование**.</span><span class="sxs-lookup"><span data-stu-id="fa93d-122">Restore the default SQL statement, if you have modified it, by clicking **Autogenerate**.</span></span>  
  
  
