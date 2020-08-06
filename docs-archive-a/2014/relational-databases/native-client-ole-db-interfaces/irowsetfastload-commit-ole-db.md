---
title: IRowsetFastLoad::Commit (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::Commit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Commit method
ms.assetid: 19de9128-b91a-4626-847f-af721edaa24e
author: rothja
ms.author: jroth
ms.openlocfilehash: cfdf355919f65fd2cedacd09249e2aae59321390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667706"
---
# <a name="irowsetfastloadcommit-ole-db"></a><span data-ttu-id="9914c-102">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="9914c-102">IRowsetFastLoad::Commit (OLE DB)</span></span>
  <span data-ttu-id="9914c-103">Обозначает конец пакета вставляемых строк и записывает эти строки в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9914c-103">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="9914c-104">Примеры можно найти в статьях [Выполнение массового копирования данных с использованием интерфейса IRowsetFastLoad (OLE DB)](irowsetfastload-ole-db.md) и [Отправка данных BLOB-объектов в SQL Server с помощью интерфейсов IROWSETFASTLOAD и ISEQUENTIALSTREAM (OLE DB)](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)</span><span class="sxs-lookup"><span data-stu-id="9914c-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9914c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9914c-105">Syntax</span></span>  
  
```  
  
HRESULT Commit(  
BOOL   
fDone  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9914c-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9914c-106">Arguments</span></span>  
 <span data-ttu-id="9914c-107">*fDone*[in]</span><span class="sxs-lookup"><span data-stu-id="9914c-107">*fDone*[in]</span></span>  
 <span data-ttu-id="9914c-108">Если значение равно FALSE, то набор строк сохраняет достоверность и может использоваться пользователем для дополнительной вставки строк.</span><span class="sxs-lookup"><span data-stu-id="9914c-108">If FALSE, the rowset maintains validity and can be used by the consumer for additional row insertion.</span></span> <span data-ttu-id="9914c-109">Если значение равно TRUE, то набор строк теряет достоверность и пользователь не может выполнять дальнейшую вставку.</span><span class="sxs-lookup"><span data-stu-id="9914c-109">If TRUE, the rowset loses validity and no further insertion can be done by the consumer.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="9914c-110">Значения кода возврата</span><span class="sxs-lookup"><span data-stu-id="9914c-110">Return Code Values</span></span>  
 <span data-ttu-id="9914c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9914c-111">S_OK</span></span>  
 <span data-ttu-id="9914c-112">Метод завершился успешно, и все добавленные записи были записаны в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9914c-112">The method succeeded and all inserted data has been written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="9914c-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9914c-113">E_FAIL</span></span>  
 <span data-ttu-id="9914c-114">Произошла ошибка, зависящая от поставщика.</span><span class="sxs-lookup"><span data-stu-id="9914c-114">A provider-specific error occurred.</span></span> <span data-ttu-id="9914c-115">Получите сведения об ошибке для конкретного текста ошибки из поставщика.</span><span class="sxs-lookup"><span data-stu-id="9914c-115">Retrieve error information for the specific error text from the provider.</span></span>  
  
 <span data-ttu-id="9914c-116">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="9914c-116">E_UNEXPECTED</span></span>  
 <span data-ttu-id="9914c-117">Этот метод был вызван применительно к набору строк массового копирования, который ранее стал недействительным в результате выполнения метода **IRowsetFastLoad::Commit**.</span><span class="sxs-lookup"><span data-stu-id="9914c-117">The method was called on a bulk copy rowset previously invalidated by the **IRowsetFastLoad::Commit** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9914c-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="9914c-118">Remarks</span></span>  
 <span data-ttu-id="9914c-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Собственный клиент OLE DB набор строк с нестандартным копированием поставщика ведет себя как набор строк режима отложенного обновления.</span><span class="sxs-lookup"><span data-stu-id="9914c-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowset behaves as a delayed-update mode rowset.</span></span> <span data-ttu-id="9914c-120">По мере вставки пользователем данных строк с помощью набора строк добавленные строки обрабатываются таким же образом, как и ожидающие выполнения вставки для набора строк, поддерживающего **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="9914c-120">As the user inserts row data through the rowset, inserted rows are treated in the same fashion as pending inserts on a rowset supporting **IRowsetUpdate**.</span></span>  
  
 <span data-ttu-id="9914c-121">Пользователь должен вызвать метод **Commit** применительно к набору строк массового копирования, чтобы записать добавленные строки в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] таким же образом, как и при использовании метода **IRowsetUpdate::Update** для отправки ожидающих строк в экземпляр SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9914c-121">The consumer must call the **Commit** method on the bulk copy rowset to write inserted rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table in the same way as the **IRowsetUpdate::Update** method is used to submit pending rows to an instance of SQL Server.</span></span>  
  
 <span data-ttu-id="9914c-122">Если пользователь освобождает ссылку на набор данных массового копирования, не вызывая метод **Commit**, то все добавленные строки, которые не были записаны, теряются.</span><span class="sxs-lookup"><span data-stu-id="9914c-122">If the consumer releases its reference on the bulk copy rowset without calling the **Commit** method, all inserted rows not previously written are lost.</span></span>  
  
 <span data-ttu-id="9914c-123">Пользователь может сгруппировать добавленные строки, вызывая метод **Commit** с аргументом *fDone* в значении FALSE.</span><span class="sxs-lookup"><span data-stu-id="9914c-123">The consumer can batch inserted rows by calling the **Commit** method with the *fDone* argument set to FALSE.</span></span> <span data-ttu-id="9914c-124">Если аргумент *fDone* установлен в значение TRUE, то набор строк становится недействительным.</span><span class="sxs-lookup"><span data-stu-id="9914c-124">When *fDone*is set to TRUE, the rowset becomes invalid.</span></span> <span data-ttu-id="9914c-125">Недействительным набором строк массового копирования поддерживаются только интерфейс **ISupportErrorInfo** и метод **IRowsetFastLoad::Release**.</span><span class="sxs-lookup"><span data-stu-id="9914c-125">An invalid bulk copy rowset supports only the **ISupportErrorInfo** interface and **IRowsetFastLoad::Release** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9914c-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9914c-126">See Also</span></span>  
 [<span data-ttu-id="9914c-127">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="9914c-127">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
