Step1:
public class BirthProvider extends ContentProvider {
Methods to Override:
onCreate() This method is called when the provider is started.

query() This method receives a request from a client. The result is returned as a Cursor object.

insert()This method inserts a new record into the content provider.

delete() This method deletes an existing record from the content provider.

update() This method updates an existing record from the content provider.

getType() This method returns the MIME type of the data at the given URI.

Step2:
<prefix>://<authority>/<data_type>/<id>

prefix
This is always set to content://

authority
This specifies the name of the content provider, for example contacts, browser etc. 
For third-party content providers, this could be the fully qualified name, 
such as com.tutorialspoint.statusprovider

data_type
This indicates the type of data that this particular provider provides. 
For example, if you are getting all the contacts from the Contacts content provider, 
then the data path would be people and URI would look like thiscontent://contacts/people

id

This specifies the specific record requested. For example, if you are looking for contact 
number 5 in the Contacts content provider then URI would look like this content://contacts/people/5.

Known Exceptions:
When exported in not true in Manifest of provider and foreign App tries to use Provider, will get following Exceptions.
Caused by: java.lang.SecurityException: Permission Denial: opening provider com.provider.app.BirthProvider from ProcessRecord{255fb47 16268:com.foreign.app/u0a392} (pid=16268, uid=10392) that is not exported from uid 10391

Room DB with Content Provider:
https://stackoverflow.com/questions/46804775/room-persistence-library-and-content-provider

