<h3><pre>TransferTO</pre></h3>

***

<span>

<sub>
<b>`Development     :`</b>    Development is completed code is available in GitHub.
<br><b>`Testing     :`</b> </h6>Testing is completed as per the API document
<br><b>`Issues      :`</b></h6>-
<br><b>`Pending     :`</b></h6>No pending items
</sub>

<h3><pre>Ezetop</pre></h3>
  Development : Development is completed code is available in GitHub.
	Testing     : Once the UAT test cases are provided by Ezetop complete testing will be performed.
	Issues      :
                      Need to setup a call with ezetop team for integration process
                      Static IP need to be finalized
                      Credentials are Not yet shared by ezetop
                      Transaction slip format not yet finalized.
	Pending     :  UAT Testing is pending.

### NepalNTC
	Development : Boiler Plate is complete 
	Testing     : Pending , waiting for the input from the support team.
	Issues      :
                       Need to know the dedicated support contact (Mail / Phone).
                       Need few clarification on URL request parameters.
                       User credentials are yet to be shared.
	Pending     :  Complete API need to be implemented.

### RemitSynergey
	Development : Only the Documentation and blue print of the methods is completed.
	Testing     : Pending
	Issues      :
                      Need to know the dedicated support contact (Mail / Phone).
                      WSDL URL is not known.
                      API supports the FTP also the details need to be discussed internally.
	Pending     : Complete API need to be implemented.

### PrepayNational
	Development : Under Development, few test cases with QA site are completed.
                      As API is developed in SCALA log4j is not implemented yet, logging
                      mechanism will be completed.
                      
	Testing     : Able to topup with the QA testing,
                      Able to topup live transaction, but the profit % and other deducation parameters
                      need to discussed - Sergey is discussing with support team. 
                      All the test cases need to be executed
                     ( API error codes )  .
	Issues      :
                       There is some profit % issue Sergey is discussing the issue with support team.
                       Sender Phone is must , do we have to hardcode the sender number or reading from a                        
                       file, as this is the requirement for most of the APIs.
	Pending     :  Test Cases, Logging mechanism , Sender Phone Number approach

### UniStream
	Development : Under Development, there is some wrong password is supplied by the unistream
                      support for jks file which is halting the development process.
                      
	Testing     : All the test cases need to be executed
                     ( API error codes )  .
	Issues      :
                       Unable to communicate with webservice, setup issue.
	Pending     :  Test Cases
                       To download the dictionaries (at least each 1 hr) from the unistream  we need to  
                       configure a job, the core logic of getting the data will be handled in java, sqlite 
                       is used for downloading dictionaries, as template is ready for the download. Ksh 
                       need to drafted.
                       Production setup document is under construction.
