LWM2M client is running and showing desired output using **Anjay LWM2M** Library. Here are the steps and results : 

* **Steps** : 

Run the following commands to install ANJAY LWM2M library :
 
   * **git clone https://github.com/AVSystem/Anjay.git**

   * **cd Anjay**

   * **git submodule update --init**

   * Now go to demo directory to make some changes in **CMakeLists.txt**. Add the following line to file so to link it with **time-space-analyser** tool.

      **add_library(ltsanalyser SHARED <path_to_time-space-analyser>/src/tsanalyser.c)**

   * Also include the following header file in demo.c which has function **getTSAnlaysis()**, which actually needs to be called inside the while loop i.e. while the client is running to print **peak RAM usage** and **Total Time Taken** : 
**#include <tsanalyser/tsanalyser.h>**

   * Now go to main Anjay directory and run the following : 

     * **cmake .**

     * **make -j**

   * Now the demo executable file will get created in the output directory so to run it do the following :
 
     * **./output/bin/demo --endpoint-name $(hostname) --server-uri $(server_uri)**

     _In place of **$(hostname)** use actual unique hostname and in place of **$(server_uri)** use actual server uri. To read about it in detail visit link : **https://avsystem.github.io/Anjay-doc/LwM2M.html**_

      I used **Leshan** open source client endpoint hostname and server uri to run the demo client i.e. : 

      **./output/bin/demo --endpoint-name 0911211322 --server-uri coap://leshan.eclipse.org:5683**

**Results** : 

![anjayclient1](https://user-images.githubusercontent.com/43041062/83680700-ed50e780-a5fe-11ea-938d-cba33ca88c90.PNG)

![anjayclient2_LI](https://user-images.githubusercontent.com/43041062/83680768-06f22f00-a5ff-11ea-9571-151b62ea7634.jpg)
