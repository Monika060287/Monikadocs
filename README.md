# Monikadocs
Set(varSpinner,false);

ClearCollect(
    colGatePassRequest,
    {
        Requestor: txtReq.Text,
        GatePass_Title: txtGPTitle.Text,    
        GatePass_Type: radGPType.Selected.Value,
 	GatePass_FromSite: drpFromSite.Selected.Value,    
        GatePass_FromAddress: txtFromAddr.Text,
	GatePass_SenderName: txtSenderGPName.Text,
        GatePass_ReturnedDate: dateReturnedDate.SelectedDate,
        GatePass_SenderPhoneNumber: txtGPPhoneNo.Text,
        GatePass_SenderEmail: txtGPEmail.Text,
        GatePass_CC: txtCostCenter.Text,
        GatePass_BusJustification: txtlBusJustify.Text,
	GatePass_ToSite:CombRecToSite.Selected.Value,
	GatePass_ToAddress:txtReceiverToAddress.Text,
	GatePass_ReceiverName:txtReceiverName.Text,
	GatePass_ReceiverPhoneNo:txtReceiverPhoneNo.Text,
	GatePass_ReceiverEmail:txtReceiverEmail.Text,
	//GatePass_AccessoriesReqd:drpAccessoriesReqd.Selected.Value,
    GatePass_AccessoriesReqd:ComboAccessReqd.Selected.Value,
	GatePass_AddUsers:txtAddUsers.Text,
    GatePass_ITAsset:drpITAsset.Selected.Value,
    GatePass_Bonded:ComboReqType.Selected.Value,
    GatePass_SiteID:varSiteID,
    GatePass_CompanyName:varCompanyName,
    GatePass_SenderStateName:varSenderStateName,
    GatePass_SenderStateCode:varSenderStateCode,
    GatePass_SenderGSTIN:varSenderGSTIN,
    GatePass_ReceiverStateName:ComboRecStateName.Selected.Value,
    GatePass_ReceiverStateCode:txtlRecStateCode.Text,
    GatePass_ReceiverGSTIN:txtRecGSTIN.Text,
    GatePass_Accessories:txtlRecAccessories2.Text,
    GatePass_ReturnTo:ComboReturnTo.Selected.Value,
    RequestorEmail:User().Email
    
        //Is_Package_Damaged: radPackageDamaged.Selected.Value
       // IWH_Request_Number:"IR-" & Text(DateValue(Today()),"yyyymmdd")&"-"&CountRows(IWH_Inward_Requests)+1
    }
);
Refresh(IWH_Process_Documents);

ClearCollect(colShowAttachmentPrev, Filter(
    IWH_Process_Documents,
    ProcessID = varSTGPRequest.IWH_STGP_RequestNo.STGP_Request_Number && Type_Of_Document = IWH_Type_Of_Document.'Standalone Request Invoices'
));

