# LWM2M-Protocol
C Library Analysis of LWM2M Protocol - Wakaama and Anjay through server-client full duplex communication.

Follow the below steps to successfully implement **Wakaama LWM2M** Server and Client and get the required properties i.e. **Peak RAM Usage**, **Total Time Taken** etc.

* **Step 1** : Go to every sub-directory in **wakaama/example** and modify the CMakeLists.txt file by adding these 2 lines : 

    * **add_library(ltsanalyser SHARED <path_to_time-space-analyser>/src/tsanalyser.c)**
    * **target_link_libraries(${PROJECT_NAME} ltsanalyser)**


_This helps in creating executable/binary files with a **linker** attached to the files_. 

* **Step 2** : Open the **lwm2mserver.c** and **lwm2mclient.c** files and include the header file : **#include <tsanalyser/tsanalyser.h>**, then also in the while loop of main function add the function **getTSAnlaysis(100)**.

_To include the function we need to include the required **header files**_ and also the **getTSAnlaysis()** functions calculates the **Peak RAM** Used and **Total Time** Taken by the process.

* **Step 3** : Now in server and then in client directory run the following : 
    * **mkdir build**
    * **cd build**
    * **cmake ..**
    * **make**

_**Cross compiling** happens and we get executable files, which is required to be done in most **embedded** related problems_.

* **Step 4** : Now we get the **lwm2mserver** and **lwm2mclient** executable files, after running them we get required result : 

**Server running** : 

![lwm2mserverscs_LI](https://user-images.githubusercontent.com/43041062/83680328-71ef3600-a5fe-11ea-99a6-c92ad938e46b.jpg)

**Client running** : 

![lwm2mclientscs_LI](https://user-images.githubusercontent.com/43041062/83680394-8af7e700-a5fe-11ea-8abe-bec1ffb08bce.jpg)



