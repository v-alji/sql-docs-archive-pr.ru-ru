---
title: Интерфейс IMDEmbedded | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 9dba8c68-4bef-4c2b-815c-c286f1a1939b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 331f8c33f7748e6591acd6d6ecda7a03ef7d8137
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657946"
---
# <a name="imdembedded-interface"></a><span data-ttu-id="2c4e9-102">Интерфейс IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="2c4e9-102">IMDEmbedded Interface</span></span>
  <span data-ttu-id="2c4e9-103">Интерфейс IMDEmbedded является открытым и служит для управления внедренной базой данных PowerPivot или шаблоном базы данных.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-103">The IMDEmbedded interface is a public interface used to manage an embedded PowerPivot database or a tabular model database.</span></span> <span data-ttu-id="2c4e9-104">Этот интерфейс наследует интерфейс `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-104">The interface inherits from the `IPersistStream` interface.</span></span> <span data-ttu-id="2c4e9-105">Этот интерфейс позволяет выполнить следующие операции:</span><span class="sxs-lookup"><span data-stu-id="2c4e9-105">The interface allows for the following operations:</span></span>  
  
-   <span data-ttu-id="2c4e9-106">Получить идентификатор внедренного потока в документе-контейнере.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-106">Get an identifier to the embedded stream in the container document.</span></span>  
  
-   <span data-ttu-id="2c4e9-107">Задать URL-адрес содержащего документа.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-107">Set the URL of the containing document.</span></span>  
  
-   <span data-ttu-id="2c4e9-108">Задать флаг, указывающий, находится ли внедряющее приложение в размещенной среде.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-108">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
-   <span data-ttu-id="2c4e9-109">Задать путь к временным файлам, используемым внедряющим приложением.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-109">Set the path to temporary files used by the embedding application.</span></span>  
  
-   <span data-ttu-id="2c4e9-110">Отменить текущую внедренную операцию.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-110">Cancel the current embedded operation.</span></span>  
  
-   <span data-ttu-id="2c4e9-111">Получить прогнозируемый размер в байтах потока для сохранения внедренного объекта.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-111">Get the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="2c4e9-112">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-112">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="2c4e9-113">Проверить, изменилась ли внедренная база данных со времени ее последнего сохранения.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-113">Verify if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="2c4e9-114">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-114">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="2c4e9-115">Загрузить внедренную базу данных в локальную или внутрипроцессную подсистему.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-115">Load the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="2c4e9-116">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-116">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="2c4e9-117">Сохранить локальную или внутрипроцессную базу данных во внедренном потоке в документе-контейнере.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-117">Save the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="2c4e9-118">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-118">Inherited from `IPersistStream`.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2c4e9-119">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="2c4e9-119">Reference</span></span>  
 <span data-ttu-id="2c4e9-120">В следующей справочной документации описывается `IMDEmbedded` интерфейс, представленный в файле заголовка **мсмд. h** .</span><span class="sxs-lookup"><span data-stu-id="2c4e9-120">The following reference documents the `IMDEmbedded` interface as presented in **msmd.h** header file.</span></span>  
  
### <a name="source-file-pxoembeddeddataidl"></a><span data-ttu-id="2c4e9-121">Исходный файл: PXOEmbeddedData.idl</span><span class="sxs-lookup"><span data-stu-id="2c4e9-121">Source file: PXOEmbeddedData.idl</span></span>  
  
```  
[  
  local,                            
  object,                           
  uuid(6B6691CF-5453-41c2-ADD9-4F320B7FD421),                       
  pointer_default(unique)           
]  
interface IMDEmbeddedData : IPersistStream  
{  
 [id(1), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in] BOOL in_fIsHosted);  
  
 [id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
  
 [id(3), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
  
 [id(4), helpstring("Set the path used by the embedding application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
  
 [id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
};  
```  
  
### <a name="imdembeddeddatagetstreamidentifier"></a><span data-ttu-id="2c4e9-122">IMDEmbeddedData::GetStreamIdentifier</span><span class="sxs-lookup"><span data-stu-id="2c4e9-122">IMDEmbeddedData::GetStreamIdentifier</span></span>  
  
```  
HRESULT GetStreamIdentifier (  
    [out, retval] BSTR * out_pbstrStreamId  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-123">Description</span></span>  
 <span data-ttu-id="2c4e9-124">Возвращает идентификатор, используемый ведущим приложением для внедренного потока в документе-контейнере.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-124">Gets the identifier used by the host application to the embedded stream in the container document.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-125">Parameters</span></span>  
 <span data-ttu-id="2c4e9-126">*out_pbstrStreamId*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-126">*out_pbstrStreamId*</span></span>  
 <span data-ttu-id="2c4e9-127">Указывает местоположение идентификатора потока.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-127">Specifies the location of the stream identifier.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="2c4e9-128">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-128">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-129">Идентификатор потока был успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-129">The stream identifier was successfully returned.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="2c4e9-130">Идентификатор потока отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-130">There is no stream identifier.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-131">При получении доступа к идентификатору потока произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-131">An error occurred accessing the stream identifier.</span></span>  
  
#### <a name="remarks"></a><span data-ttu-id="2c4e9-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c4e9-132">Remarks</span></span>  
 <span data-ttu-id="2c4e9-133">Чтобы проверить, содержит ли текущее соединение внедренную базу данных, пользователь должен проверить значение свойства DBPROP_MSMD_EMBEDDED_DATA, являющееся одним из свойств соединения OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-133">To verify if the current connection contains an embedded database, the user should check the value of the DBPROP_MSMD_EMBEDDED_DATA property from the OLE DB connection properties.</span></span>  
  
 <span data-ttu-id="2c4e9-134">Возможные значения для DBPROP_MSMD_EMBEDDED_DATA.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-134">The possible values for DBPROP_MSMD_EMBEDDED_DATA are:</span></span>  
  
|<span data-ttu-id="2c4e9-135">Имя</span><span class="sxs-lookup"><span data-stu-id="2c4e9-135">Name</span></span>|<span data-ttu-id="2c4e9-136">Значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-136">Value</span></span>|<span data-ttu-id="2c4e9-137">Определение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-137">Definition</span></span>|  
|----------|-----------|----------------|  
|<span data-ttu-id="2c4e9-138">DBPROPVAL_EMBED_NONE</span><span class="sxs-lookup"><span data-stu-id="2c4e9-138">DBPROPVAL_EMBED_NONE</span></span>|<span data-ttu-id="2c4e9-139">0x00</span><span class="sxs-lookup"><span data-stu-id="2c4e9-139">0x00</span></span>|<span data-ttu-id="2c4e9-140">Доступная внедренная база данных отсутствует</span><span class="sxs-lookup"><span data-stu-id="2c4e9-140">No embedded database available</span></span>|  
|<span data-ttu-id="2c4e9-141">DBPROPVAL_EMBED_EMBEDDED</span><span class="sxs-lookup"><span data-stu-id="2c4e9-141">DBPROPVAL_EMBED_EMBEDDED</span></span>|<span data-ttu-id="2c4e9-142">0x01</span><span class="sxs-lookup"><span data-stu-id="2c4e9-142">0x01</span></span>|<span data-ttu-id="2c4e9-143">Текущее приложение содержит внедренную базу данных</span><span class="sxs-lookup"><span data-stu-id="2c4e9-143">The current application contains the embedded database</span></span>|  
|<span data-ttu-id="2c4e9-144">DBPROPVAL_EMBED_LINKED</span><span class="sxs-lookup"><span data-stu-id="2c4e9-144">DBPROPVAL_EMBED_LINKED</span></span>|<span data-ttu-id="2c4e9-145">0x02</span><span class="sxs-lookup"><span data-stu-id="2c4e9-145">0x02</span></span>|<span data-ttu-id="2c4e9-146">Внедренная база данных размещена в удаленном приложении (т. е. на сервере SharePoint)</span><span class="sxs-lookup"><span data-stu-id="2c4e9-146">The embedded database is hosted in a remote application (i.e. SharePoint Server)</span></span>|  
  
#### <a name="source"></a><span data-ttu-id="2c4e9-147">Источник</span><span class="sxs-lookup"><span data-stu-id="2c4e9-147">Source</span></span>  
  
```  
[id(1), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
```  
  
### <a name="imdembeddeddatasetcontainerurl"></a><span data-ttu-id="2c4e9-148">IMDEmbeddedData::SetContainerURL</span><span class="sxs-lookup"><span data-stu-id="2c4e9-148">IMDEmbeddedData::SetContainerURL</span></span>  
  
```  
HRESULT SetContainerURL (  
    [in] BSTR in_bstrURL  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-149">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-149">Description</span></span>  
 <span data-ttu-id="2c4e9-150">Задает URL-адрес для файла, содержащего внедренный поток.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-150">Sets the URL for the file containing the embedded stream.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-151">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-151">Parameters</span></span>  
 <span data-ttu-id="2c4e9-152">*in_bstrURL*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-152">*in_bstrURL*</span></span>  
 <span data-ttu-id="2c4e9-153">Указывает URL-адрес для содержащего документа.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-153">Specifies the URL for the containing document.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="2c4e9-154">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-154">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-155">URL-адрес контейнера был успешно задан.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-155">The container URL was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-156">При задании URL-адреса контейнера произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-156">An error occurred while setting the container URL.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="2c4e9-157">Источник</span><span class="sxs-lookup"><span data-stu-id="2c4e9-157">Source</span></span>  
  
```  
[id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
```  
  
### <a name="imdembeddeddatasethosted"></a><span data-ttu-id="2c4e9-158">IMDEmbeddedData::SetHosted</span><span class="sxs-lookup"><span data-stu-id="2c4e9-158">IMDEmbeddedData::SetHosted</span></span>  
  
```  
HRESULT SetHosted (  
    [in] BOOL in_fIsHosted  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-159">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-159">Description</span></span>  
 <span data-ttu-id="2c4e9-160">Задать флаг, указывающий, находится ли внедряющее приложение в размещенной среде.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-160">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-161">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-161">Parameters</span></span>  
 <span data-ttu-id="2c4e9-162">*in_ftHosted*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-162">*in_ftHosted*</span></span>  
 <span data-ttu-id="2c4e9-163">TRUE, если вызывающий объект находится в приложении, размещенном в службе (например IIS).</span><span class="sxs-lookup"><span data-stu-id="2c4e9-163">TRUE if caller is in a hosted in a service application (like IIS).</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="2c4e9-164">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-164">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-165">Флаг был успешно задан.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-165">The flag was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-166">При задании флага произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-166">An error occurred while setting the flag.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="2c4e9-167">Источник</span><span class="sxs-lookup"><span data-stu-id="2c4e9-167">Source</span></span>  
  
```  
[id(5), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in]  BOOL in_fIsHosted);  
```  
  
### <a name="imdembeddeddatasettempdirpath"></a><span data-ttu-id="2c4e9-168">IMDEmbeddedData::SetTempDirPath</span><span class="sxs-lookup"><span data-stu-id="2c4e9-168">IMDEmbeddedData::SetTempDirPath</span></span>  
  
```  
HRESULT SetTempDirPath (  
    [in] BSTR in_bstrPath  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-169">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-169">Description</span></span>  
 <span data-ttu-id="2c4e9-170">Задать путь к временным файлам, используемым внедряющим приложением.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-170">Set the path to temporary files used by the embedding application.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-171">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-171">Parameters</span></span>  
 <span data-ttu-id="2c4e9-172">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-172">*in_bstrPath*</span></span>  
 <span data-ttu-id="2c4e9-173">Путь, используемый ведущим приложением для временных файлов.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-173">The path used by the host application for temporary files.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="2c4e9-174">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-174">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-175">Каталог временного файла был успешно задан.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-175">The temporary file directory was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-176">При задании пути произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-176">An error occurred while setting the path.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="2c4e9-177">Источник</span><span class="sxs-lookup"><span data-stu-id="2c4e9-177">Source</span></span>  
  
```  
[id(4), helpstring("Set the path used by the host application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
```  
  
### <a name="imdembeddeddatacancel"></a><span data-ttu-id="2c4e9-178">IMDEmbeddedData::Cancel</span><span class="sxs-lookup"><span data-stu-id="2c4e9-178">IMDEmbeddedData::Cancel</span></span>  
  
```  
HRESULT Cancel ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-179">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-179">Description</span></span>  
 <span data-ttu-id="2c4e9-180">Отменяет текущую операцию внедренной базы данных</span><span class="sxs-lookup"><span data-stu-id="2c4e9-180">Cancels the current embedded database operation</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-181">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-181">Parameters</span></span>  
 <span data-ttu-id="2c4e9-182">Нет.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-182">None.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="2c4e9-183">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-183">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-184">Операция была успешно отменена.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-184">The operation was successfully cancelled.</span></span>  
  
 `DB_E_CANTCANCEL`  
 <span data-ttu-id="2c4e9-185">В настоящее время не выполняется ни одна операция, которую можно отменить.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-185">No cancellable operation is currently in progress.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-186">При отмене внедренной операции произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-186">An error occurred while cancelling the embedded operation.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="2c4e9-187">Источник</span><span class="sxs-lookup"><span data-stu-id="2c4e9-187">Source</span></span>  
  
```  
[id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
```  
  
### <a name="imdembeddeddatagetsizemax-ipersiststreamgetsizemax"></a><span data-ttu-id="2c4e9-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span><span class="sxs-lookup"><span data-stu-id="2c4e9-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span></span>  
  
```  
HRESULT GetSizeMax (  
    [out] ULARGE_INTEGER * out_pcbSize  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-189">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-189">Description</span></span>  
 <span data-ttu-id="2c4e9-190">Возвращает прогнозируемый размер в байтах потока для сохранения внедренного объекта.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-190">Gets the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="2c4e9-191">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-191">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-192">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-192">Parameters</span></span>  
 <span data-ttu-id="2c4e9-193">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-193">*in_bstrPath*</span></span>  
 <span data-ttu-id="2c4e9-194">Прогнозируемый размер в байтах образа внедренной базы данных.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-194">The estimated size (in bytes) of the embedded database image.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="2c4e9-195">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2c4e9-195">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-196">Размер был успешно получен.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-196">The size was successfully obtained.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-197">При получении размера произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-197">An error occurred while obtaining the size.</span></span>  
  
### <a name="imdembeddeddataisdirty-ipersiststreamisdirty"></a><span data-ttu-id="2c4e9-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span><span class="sxs-lookup"><span data-stu-id="2c4e9-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span></span>  
  
```  
HRESULT IsDirty ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-199">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-199">Description</span></span>  
 <span data-ttu-id="2c4e9-200">Проверяет, изменилась ли внедренная база данных со времени последнего сохранения.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-200">Verifies if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="2c4e9-201">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-201">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-202">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-202">Parameters</span></span>  
 <span data-ttu-id="2c4e9-203">none</span><span class="sxs-lookup"><span data-stu-id="2c4e9-203">none</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="2c4e9-204">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="2c4e9-204">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-205">База данных изменилась со времени последнего сохранения.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-205">The database has changed since it was last saved.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="2c4e9-206">База данных не изменилась со времени последнего сохранения.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-206">The database has not changed since it was last saved.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-207">При получении состояния базы данных произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-207">An error occurred while obtaining the database state.</span></span>  
  
### <a name="imdembeddeddataload-ipersiststreamload"></a><span data-ttu-id="2c4e9-208">IMDEmbeddedData::Load (IPersistStream::Load)</span><span class="sxs-lookup"><span data-stu-id="2c4e9-208">IMDEmbeddedData::Load (IPersistStream::Load)</span></span>  
  
```  
HRESULT Load (   
    [in] IStream * in_pStm   
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-209">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-209">Description</span></span>  
 <span data-ttu-id="2c4e9-210">Загружает внедренную базу данных в локальную или внутрипроцессную подсистему.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-210">Loads the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="2c4e9-211">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-211">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-212">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-212">Parameters</span></span>  
 <span data-ttu-id="2c4e9-213">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-213">*in_pStm*</span></span>  
 <span data-ttu-id="2c4e9-214">Указатель на интерфейс потока, из которого должна быть загружена внедренная база данных.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-214">A pointer to a stream interface from where to load the embedded database.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="2c4e9-215">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="2c4e9-215">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-216">База данных была успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-216">The database was successfully loaded.</span></span>  
  
 `E_OUTOFMEMORY`  
 <span data-ttu-id="2c4e9-217">Недостаточно памяти для загрузки базы данных.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-217">Not enough memory to load the database.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="2c4e9-218">При загрузке базы данных произошла ошибка, отличная от `E_OUTOFMEMORY`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-218">An error occurred while loading the database, different than `E_OUTOFMEMORY`.</span></span>  
  
### <a name="imdembeddeddatasave-ipersiststreamsave"></a><span data-ttu-id="2c4e9-219">IMDEmbeddedData::Save (IPersistStream::Save)</span><span class="sxs-lookup"><span data-stu-id="2c4e9-219">IMDEmbeddedData::Save (IPersistStream::Save)</span></span>  
  
```  
HRESULT Save (   
    [in] IStream * in_pStm,  
    [in] BOOL in_fClearDirty  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="2c4e9-220">Описание</span><span class="sxs-lookup"><span data-stu-id="2c4e9-220">Description</span></span>  
 <span data-ttu-id="2c4e9-221">Сохраняет локальную или внутрипроцессную базу данных во внедренном потоке в документе-контейнере.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-221">Saves the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="2c4e9-222">Наследуется от `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-222">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2c4e9-223">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c4e9-223">Parameters</span></span>  
 <span data-ttu-id="2c4e9-224">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-224">*in_pStm*</span></span>  
 <span data-ttu-id="2c4e9-225">Указатель на интерфейс потока, в который должна быть сохранена внедренная база данных.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-225">A pointer to a stream interface to where to save the embedded database.</span></span>  
  
 <span data-ttu-id="2c4e9-226">*in_fClearDirty*</span><span class="sxs-lookup"><span data-stu-id="2c4e9-226">*in_fClearDirty*</span></span>  
 <span data-ttu-id="2c4e9-227">Флаг, который указывает, должен ли флаг «грязных» данных быть очищен после этой операции.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-227">A flag that indicates whether the dirty flag should be cleared after this operation.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="2c4e9-228">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="2c4e9-228">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="2c4e9-229">База данных была успешно сохранена.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-229">The database was successfully saved.</span></span>  
  
 `STG_E_CANTSAVE`  
 <span data-ttu-id="2c4e9-230">Во время сохранения базы данных произошла ошибка, отличная от `STG_E_MEDIUMFULL`.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-230">An error occurred while saving the database, different than `STG_E_MEDIUMFULL`.</span></span>  
  
 `STG_E_MEDIUMFULL`  
 <span data-ttu-id="2c4e9-231">База данных не могла быть сохранена, поскольку на запоминающем устройстве не осталось места.</span><span class="sxs-lookup"><span data-stu-id="2c4e9-231">The database could not be saved because there is no space left on the storage device.</span></span>  
  
  
