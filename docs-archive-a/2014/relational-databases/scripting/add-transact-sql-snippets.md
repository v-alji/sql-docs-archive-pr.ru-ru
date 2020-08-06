---
title: Добавление фрагментов кода Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b5886f8f36ae3753fcb7c89dd3aeff9c69eeba5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658181"
---
# <a name="add-transact-sql-snippets"></a><span data-ttu-id="b4260-102">Добавление фрагментов кода Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4260-102">Add Transact-SQL Snippets</span></span>
  <span data-ttu-id="b4260-103">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]можно добавить собственные фрагменты кода Transact-SQL в набор предварительно определенных фрагментов.</span><span class="sxs-lookup"><span data-stu-id="b4260-103">You can add your own Transact-SQL code snippets to the set of pre-defined snippets included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="creating-a-transact-sql-snippet-file"></a><span data-ttu-id="b4260-104">Создание файла фрагмента Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4260-104">Creating a Transact-SQL Snippet File</span></span>  
 <span data-ttu-id="b4260-105">Первая часть создания фрагмента кода [!INCLUDE[tsql](../../includes/tsql-md.md)] заключается в создании XML-файла с текстом фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="b4260-105">The first part of creating a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet.</span></span> <span data-ttu-id="b4260-106">Файл должен иметь расширение SNIPPET и отвечать требованиям [Схемы фрагментов кода](https://go.microsoft.com/fwlink/?LinkId=207504).</span><span class="sxs-lookup"><span data-stu-id="b4260-106">The file must have a .snippet file extension, and meet the requirements of the [Code Snippets Schema](https://go.microsoft.com/fwlink/?LinkId=207504).</span></span> <span data-ttu-id="b4260-107">Укажите SQL в качестве языка фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="b4260-107">Set the snippet language to SQL.</span></span>  
  
 <span data-ttu-id="b4260-108">Можно использовать предварительно определенные фрагменты, которые поставляются вместе с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в качестве примеров.</span><span class="sxs-lookup"><span data-stu-id="b4260-108">You can use the pre-defined snippets that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as examples.</span></span> <span data-ttu-id="b4260-109">Чтобы найти предустановленные фрагменты кода, откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем в меню **Сервис** выберите пункт **Диспетчер фрагментов кода**.</span><span class="sxs-lookup"><span data-stu-id="b4260-109">To find the pre-defined snippets, open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Tools** menu, and click **Code Snippet Manager**.</span></span> <span data-ttu-id="b4260-110">Выберите **SQL** из списка полей **Язык** , путь к фрагментам [!INCLUDE[tsql](../../includes/tsql-md.md)] отображается в поле **Расположение** .</span><span class="sxs-lookup"><span data-stu-id="b4260-110">Select **SQL** in the **Language** list box, the path to the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippets is displayed in the **Location** box.</span></span>  
  
## <a name="registering-the-code-snippet"></a><span data-ttu-id="b4260-111">Регистрация фрагмента кода</span><span class="sxs-lookup"><span data-stu-id="b4260-111">Registering the Code Snippet</span></span>  
 <span data-ttu-id="b4260-112">После создания файла фрагмента используйте диспетчер фрагментов кода для регистрации фрагмента с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4260-112">After creating the snippet file, use the Code Snippets Manager to register the snippet with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b4260-113">Можно либо добавить папку, содержащую несколько фрагментов, либо импортировать отдельные фрагменты в папку **Мои фрагменты кода** .</span><span class="sxs-lookup"><span data-stu-id="b4260-113">You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b4260-114">Процедуры</span><span class="sxs-lookup"><span data-stu-id="b4260-114">Procedures</span></span>  
  
#### <a name="adding-a-snippet-folder"></a><span data-ttu-id="b4260-115">Добавление папки фрагментов</span><span class="sxs-lookup"><span data-stu-id="b4260-115">Adding a Snippet Folder</span></span>  
  
1.  <span data-ttu-id="b4260-116">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4260-116">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4260-117">Выберите меню **Сервис** и нажмите кнопку **Диспетчер фрагментов кода**.</span><span class="sxs-lookup"><span data-stu-id="b4260-117">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="b4260-118">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b4260-118">Click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="b4260-119">Перейдите к папке, содержащей собственные фрагменты кода, и нажмите кнопку **Выбор папки** .</span><span class="sxs-lookup"><span data-stu-id="b4260-119">Navigate to the folder containing your code snippets, and click the **Select Folder** button.</span></span>  
  
#### <a name="importing-a-snippet"></a><span data-ttu-id="b4260-120">Импорт фрагмента</span><span class="sxs-lookup"><span data-stu-id="b4260-120">Importing a Snippet</span></span>  
  
1.  <span data-ttu-id="b4260-121">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4260-121">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="b4260-122">Выберите меню **Сервис** и нажмите кнопку **Диспетчер фрагментов кода**.</span><span class="sxs-lookup"><span data-stu-id="b4260-122">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="b4260-123">Нажмите кнопку **Import** (Импортировать).</span><span class="sxs-lookup"><span data-stu-id="b4260-123">Click the **Import** button.</span></span>  
  
4.  <span data-ttu-id="b4260-124">Перейдите к папке, содержащей собственный фрагмент кода, выберите файл с расширением SNIPPET и нажмите кнопку **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="b4260-124">Navigate to the folder containing your snippet, click on the .snippet file, and click the **Open** button.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b4260-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="b4260-125">Examples</span></span>  
 <span data-ttu-id="b4260-126">В следующем примере создается окружающий блок `TRY-CATCH` для фрагмента кода, который будет импортирован в среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4260-126">The following example creates a `TRY-CATCH` surround-with snippet and imports it to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="b4260-127">Вставьте следующий код в блокнот, сохраните файл с именем TryCatch.snippet.</span><span class="sxs-lookup"><span data-stu-id="b4260-127">Paste the following code into notepad, then save as a file named TryCatch.snippet.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="https://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  <span data-ttu-id="b4260-128">Откройте среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4260-128">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="b4260-129">Выберите меню **Сервис** и нажмите кнопку **Диспетчер фрагментов кода**.</span><span class="sxs-lookup"><span data-stu-id="b4260-129">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
4.  <span data-ttu-id="b4260-130">Нажмите кнопку **Import** (Импортировать).</span><span class="sxs-lookup"><span data-stu-id="b4260-130">Click the **Import** button.</span></span>  
  
5.  <span data-ttu-id="b4260-131">Перейдите к папке, содержащей файл TryCatch.snippet, щелкните файл TryCatch.snippet и нажмите кнопку **Открыть** .</span><span class="sxs-lookup"><span data-stu-id="b4260-131">Navigate to the folder containing TryCatch.snippet, click on the TryCatch.snippet file, and click the **Open** button.</span></span> <span data-ttu-id="b4260-132">В папке **Мои фрагменты кода** не должно быть фрагмента TryCatch.</span><span class="sxs-lookup"><span data-stu-id="b4260-132">You should not have a TryCatch snippet in your **My Code Snippets** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4260-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4260-133">See Also</span></span>  
 [<span data-ttu-id="b4260-134">Вставка фрагментов кода окружения Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b4260-134">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
