TO demonstrate MVVM in BLE
LeConnectedActivity will receive broadcast from Service. The using viewmodel in LeConnectedActivity for monitoring stateconnection. 
This project is using viewpager fragment to navigate to other page. The connection will still retrieve to the sameviewmodel using 
SharedViewModel .

But the problem when you are using Activity to navigate to new page. The connection is not appear and the viewmodel in the activity fail to retrieve the data .You can use popup menu option and you will notice that the connection will be lost.

This project also the connection is not stable . Already binding the service but will connect & disconnect automatically.

Fork Project# Thesis
Android app that reads sensors' (Grove temperature sensor v1.2 + MQ-135 gas sensor) data from the BLE shield by RedBearLab, which is mounted on Arduino Uno. The measurements can be exchanged with 'SaMi' cloud service of Savonia UAS. 


Current implementation:

MVVM architectural pattern with central repository was used to split the app in different modules as advised by Google.
The sensors' data is persisted in the Room by background BLE service. ViewModel observes changes in the repository with help of LiveData. The UI subscribes to data changes in the ViewModel.
ViewPager in combination with FragmentPagerAdapter are used to build UI with graphs (using GraphView library). The fragments retain their states after configuration changes and reload previously observed data from the DB if the app is relaunched.
The measurements can be offloaded to Savonia measurements service (SaMi) throug Retrofit web client. The database gets cleared afterwards. Also, the data can be retrieved from the cloud through Retrofit and displayed on the graphs.
