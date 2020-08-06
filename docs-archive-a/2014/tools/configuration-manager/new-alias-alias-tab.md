---
title: Создать псевдоним (вкладка "псевдоним") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90742e5de3da0cac83c8b18eebba242ddb9a865d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659049"
---
# <a name="new-alias-alias-tab"></a><span data-ttu-id="1c054-102">Создание псевдонима (вкладка «Псевдоним»)</span><span class="sxs-lookup"><span data-stu-id="1c054-102">New Alias (Alias Tab)</span></span>
  <span data-ttu-id="1c054-103">Псевдоним является альтернативным именем, которое можно использовать для создания соединения.</span><span class="sxs-lookup"><span data-stu-id="1c054-103">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="1c054-104">Псевдоним инкапсулирует необходимые элементы строки соединения и представляет их с помощью имени, выбранного пользователем.</span><span class="sxs-lookup"><span data-stu-id="1c054-104">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="1c054-105">Используйте страницу **Псевдоним** в диалоговом окне **Псевдоним — новый** , чтобы задать элементы строки подключения для псевдонима.</span><span class="sxs-lookup"><span data-stu-id="1c054-105">Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias.</span></span> <span data-ttu-id="1c054-106">Сведения об изменении строки подключения существующего псевдонима см. в разделе [Свойства &#60;Псевдоним&#62; (вкладка "Псевдоним")](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span><span class="sxs-lookup"><span data-stu-id="1c054-106">To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span></span>  
  
 <span data-ttu-id="1c054-107">Необязательно заполнять все значения в сетке **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="1c054-107">All values in the **Properties** grid do not have to be completed.</span></span> <span data-ttu-id="1c054-108">Допустимые сочетания значений зависят от выбранного протокола.</span><span class="sxs-lookup"><span data-stu-id="1c054-108">Valid combinations vary depending on the protocol selected.</span></span> <span data-ttu-id="1c054-109">Примеры допустимых сочетаний см. в разделах, приведенных ниже.</span><span class="sxs-lookup"><span data-stu-id="1c054-109">See the topics listed below for examples of valid combinations.</span></span>  
  
 <span data-ttu-id="1c054-110">**Имя псевдонима**</span><span class="sxs-lookup"><span data-stu-id="1c054-110">**Alias Name**</span></span>  
 <span data-ttu-id="1c054-111">Имя (псевдоним), которое будет использоваться для ссылки на это соединение.</span><span class="sxs-lookup"><span data-stu-id="1c054-111">The name (alias) that you want to use to refer to this connection.</span></span>  
  
 <span data-ttu-id="1c054-112">**Имя канала** / **Номер порта**</span><span class="sxs-lookup"><span data-stu-id="1c054-112">**Pipe Name** / **Port No**</span></span>  
 <span data-ttu-id="1c054-113">Дополнительные элементы строки подключения.</span><span class="sxs-lookup"><span data-stu-id="1c054-113">Additional elements of the connection string.</span></span> <span data-ttu-id="1c054-114">Имя этого поля зависит от выбранного протокола.</span><span class="sxs-lookup"><span data-stu-id="1c054-114">The name of this box varies with the selected protocol.</span></span>  
  
 <span data-ttu-id="1c054-115">**Протокол**</span><span class="sxs-lookup"><span data-stu-id="1c054-115">**Protocol**</span></span>  
 <span data-ttu-id="1c054-116">Протокол, используемый для соединения.</span><span class="sxs-lookup"><span data-stu-id="1c054-116">The protocol used for the connection.</span></span>  
  
 <span data-ttu-id="1c054-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="1c054-117">**Server**</span></span>  
 <span data-ttu-id="1c054-118">Имя экземпляра [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], к которому выполняется подключение.</span><span class="sxs-lookup"><span data-stu-id="1c054-118">The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.</span></span>  
  
## <a name="when-to-use-an-alias"></a><span data-ttu-id="1c054-119">Использование псевдонима</span><span class="sxs-lookup"><span data-stu-id="1c054-119">When to Use an Alias</span></span>  
 <span data-ttu-id="1c054-120">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] подключается к локальному экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью протокола **Общая память** и к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на другом компьютере с помощью протокола **TCP/IP** или **Именованные каналы**.</span><span class="sxs-lookup"><span data-stu-id="1c054-120">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**.</span></span> <span data-ttu-id="1c054-121">Создайте псевдоним, если во время использования протокола TCP/IP или именованных каналов необходимо вводить пользовательскую строку подключения или если для соединения нужно использовать имя, отличное от имени сервера.</span><span class="sxs-lookup"><span data-stu-id="1c054-121">Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="1c054-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="1c054-122">Examples</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1c054-123">не прослушивает установленный по умолчанию порт TCP/IP под номером 1433, поэтому необходимо использовать строку подключения с другим номером порта.</span><span class="sxs-lookup"><span data-stu-id="1c054-123">is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1c054-124">не прослушивает именованный канал по умолчанию, поэтому необходимо использовать строку соединения с другим именем канала.</span><span class="sxs-lookup"><span data-stu-id="1c054-124">is not listening on the default named pipe so you want to provide a connection string with a different pipe name.</span></span>  
  
-   <span data-ttu-id="1c054-125">Приложение ожидает подключения к базе данных на сервере с именем `ACCT`, но эта база данных прошла консолидацию в виде экземпляра с именем `ACCT` на сервере с именем `CENTRAL`.</span><span class="sxs-lookup"><span data-stu-id="1c054-125">An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`.</span></span> <span data-ttu-id="1c054-126">Приложение нельзя легко изменить.</span><span class="sxs-lookup"><span data-stu-id="1c054-126">The application cannot easily be changed.</span></span> <span data-ttu-id="1c054-127">Создайте псевдоним с именем `ACCT`и со строкой соединения, указывающей на `CENTRAL\ACCT`.</span><span class="sxs-lookup"><span data-stu-id="1c054-127">Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.</span></span>  
  
## <a name="creating-a-valid-connection-string"></a><span data-ttu-id="1c054-128">Создание допустимой строки соединения</span><span class="sxs-lookup"><span data-stu-id="1c054-128">Creating a Valid Connection String</span></span>  
 <span data-ttu-id="1c054-129">Описание и примеры допустимых сочетаний свойств псевдонима см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1c054-129">See the following topics for a description and examples of valid combinations of alias properties:</span></span>  
  
-   [<span data-ttu-id="1c054-130">Создание допустимой строки соединения с использованием протокола общей памяти</span><span class="sxs-lookup"><span data-stu-id="1c054-130">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [<span data-ttu-id="1c054-131">Создание допустимой строки подключения с использованием протокола TCP/IP</span><span class="sxs-lookup"><span data-stu-id="1c054-131">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [<span data-ttu-id="1c054-132">Создание допустимой строки подключения, использующей протокол именованных каналов</span><span class="sxs-lookup"><span data-stu-id="1c054-132">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
