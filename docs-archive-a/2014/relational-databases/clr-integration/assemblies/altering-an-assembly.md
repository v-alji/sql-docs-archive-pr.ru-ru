---
title: Изменение сборки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: c22ca979675d3b7f263e3bc6de0c41c134a1abcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735341"
---
# <a name="altering-an-assembly"></a><span data-ttu-id="06a08-102">Изменение сборки</span><span class="sxs-lookup"><span data-stu-id="06a08-102">Altering an Assembly</span></span>
  <span data-ttu-id="06a08-103">Сборку, зарегистрированную в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], можно обновить до более поздней версии при помощи инструкции ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="06a08-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can be updated from a more recent version using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="06a08-104">Для этого применяется следующий синтаксис инструкции ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="06a08-104">To update an assembly, use the ALTER ASSEMBLY statement with the following syntax:</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 <span data-ttu-id="06a08-105">Инструкция ALTER ASSEMBLY не прерывает выполняемые процессы, в которых используются эта сборка, — они продолжают использовать ее прежнюю версию.</span><span class="sxs-lookup"><span data-stu-id="06a08-105">ALTER ASSEMBLY does not disrupt currently running processes that are using the assembly; the processes continue executing with the unaltered assembly.</span></span> <span data-ttu-id="06a08-106">Инструкция ALTER ASSEMBLY не может быть использована для изменения подписи функций среды CLR, агрегатных функций, хранимых процедур и триггеров.</span><span class="sxs-lookup"><span data-stu-id="06a08-106">ALTER ASSEMBLY cannot be used to change the signatures of common language runtime (CLR) functions, aggregate functions, stored procedures, and triggers.</span></span> <span data-ttu-id="06a08-107">К сборке могут быть добавлены новые общие методы, частные методы могут быть каким угодно образом изменены, а общие могут быть изменены при условии неизменности их подписей и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="06a08-107">New public methods can be added to the assembly, private methods can be modified in any way, and public methods can be modified as long as signatures or attributes are not changed.</span></span> <span data-ttu-id="06a08-108">Поля в определяемом пользователем типе с собственной сериализацией, в том числе элементы данных или основные классы, нельзя изменить с помощью ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="06a08-108">Fields that are contained within a native-serialized user-defined type, including data members or base classes, cannot be changed by using ALTER ASSEMBLY.</span></span> <span data-ttu-id="06a08-109">Любые другие изменения не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="06a08-109">All other changes are unsupported.</span></span> <span data-ttu-id="06a08-110">Дополнительные сведения см. в разделе [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="06a08-110">For more information, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
## <a name="changing-the-permission-set-of-an-assembly"></a><span data-ttu-id="06a08-111">Изменение набора разрешений для сборки</span><span class="sxs-lookup"><span data-stu-id="06a08-111">Changing the Permission Set of an Assembly</span></span>  
 <span data-ttu-id="06a08-112">Набор разрешений для сборки можно также изменить с помощью инструкции ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="06a08-112">The permission set of an assembly can also be changed using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="06a08-113">Следующая инструкция меняет набор разрешений сборки SQLCLRTest на `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="06a08-113">The following statement changes the permission set of the SQLCLRTest assembly to `EXTERNAL_ACCESS`.</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 <span data-ttu-id="06a08-114">Если набор разрешений сборки меняется с `SAFE` на `EXTERNAL_ACCESS` или `UNSAFE`, то необходимо вначале создать для сборки ассиметричный ключ и соответствующее имя входа с разрешением `EXTERNAL ACCESS ASSEMBLY` или `UNSAFE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="06a08-114">If the permission set of an assembly is being changed from `SAFE` to `EXTERNAL_ACCESS` or `UNSAFE`, an asymmetric key and corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission or `UNSAFE ASSEMBLY` permission for the assembly must first be created.</span></span> <span data-ttu-id="06a08-115">Дополнительные сведения см. в статье [Creating an Assembly](creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="06a08-115">For more information, see [Creating an Assembly](creating-an-assembly.md).</span></span>  
  
## <a name="adding-the-source-code-of-an-assembly"></a><span data-ttu-id="06a08-116">Дополнение исходного кода в сборку</span><span class="sxs-lookup"><span data-stu-id="06a08-116">Adding the Source Code of an Assembly</span></span>  
 <span data-ttu-id="06a08-117">Предложение ADD FILE в синтаксисе инструкции ALTER ASSEMBLY отсутствует в инструкции CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="06a08-117">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="06a08-118">Оно обеспечивает возможность добавления исходного кода или любых других файлов, связанных со сборкой.</span><span class="sxs-lookup"><span data-stu-id="06a08-118">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="06a08-119">Файлы копируются из исходных расположений и сохраняются в системных таблицах базы данных.</span><span class="sxs-lookup"><span data-stu-id="06a08-119">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="06a08-120">Это обеспечивает постоянную доступность исходного кода или других файлов на тот случай, если возникнет необходимость повторного создания или документирования текущей версии определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="06a08-120">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="06a08-121">Следующая инструкция добавляет исходный код класса Point.cs к сборке Point UDT.</span><span class="sxs-lookup"><span data-stu-id="06a08-121">The following statement adds the Point.cs class source code for the Point UDT.</span></span> <span data-ttu-id="06a08-122">В результате этого текст, содержащийся в файле Point.cs, будет скопирован и сохранен в базе данных с именем PointSource.</span><span class="sxs-lookup"><span data-stu-id="06a08-122">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a><span data-ttu-id="06a08-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="06a08-123">See Also</span></span>  
 <span data-ttu-id="06a08-124">[Управление сборками интеграции со средой CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="06a08-124">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="06a08-125">[Создание сборки](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="06a08-125">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="06a08-126">[Удаление сборки](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="06a08-126">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 [<span data-ttu-id="06a08-127">ALTER ASSEMBLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="06a08-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
  
