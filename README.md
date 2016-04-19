App Dev Cloud with JBoss BPM Travel Agency Demo
===============================================
This demo is to install JBoss BPM Suite Mortgage Demo in the Cloud based on leveraging the Red Hat 
Container Development Kit (CDK) and the provided OpenShift Enterprise (OSE) image. 
It delivers a fully functioning JBoss BPM Mortgage example containerized on OSE.

This is an online employee travel booking process project. It contains multiple web services for looking up data for the process
and rules to calculate pricing. Furthermore, there are several tasks that can be activated to evaluate pricing and to review the
final booking data before completing the booking.


Install on Red Hat CDK OpenShift Enterprise image
-------------------------------------------------
1. First complete the installation and start the OpenShift image supplied in the [cdk-install-demo](https://github.com/redhatdemocentral/cdk-install-demo).

2. Install [OpenShift Client Tools](https://developers.openshift.com/managing-your-applications/client-tools.html) if you have not done so previously.

2. [Download and unzip this demo.](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/archive/master.zip)

3. Add products to installs directory.

5. Run 'init.sh' or 'init.bat' file. 'init.bat' must be run with Administrative privileges.

6. Login to JBoss BPM Suite to start exploring a travel agency booking project:

    [http://rhcs-travel-agency-demo.10.1.2.2.xip.io/business-central](http://rhcs-travel-agency-demo.10.1.2.2.xip.io/business-central)
    ( u:erics / p:bpmsuite1! )

    [http://rhcs-travel-agency-demo.10.1.2.2.xip.io/external-client-ui-form-1.0](http://rhcs-travel-agency-demo.10.1.2.2.xip.io/external-client-ui-form-1.0)


Notes
-----
Should your local network DNS not handle the resolution of the above address, giving you page not found errors, you can apply the
following to your local hosts file:

    ```
    $ sudo vi /etc/hosts

    # add host for CDK demo resolution.
    10.1.2.2   rhcs-travel-agency-demo.10.1.2.2.xip.io    rhcs-travel-agency-demo.10.1.2.2.xip.io
    ```


Booking a trip to Edinburgh (just one scenario)
-----------------------------------------------
1. Build & deploy project.

2. Start process with following data in start form (either from JBoss BPM Suite dashboard or using external client UI deployed at [http://rhcs-travel-agency-demo.10.1.2.2.xip.io/external-client-ui-form-1.0](http://rhcs-travel-agency-demo.10.1.2.2.xip.io/external-client-ui-form-1.0):

  ```
  Name: [your-name]

  Email Adress: [any-email]

  Number of Travellers: 2  

  From Destination: London

  To Destination: Edinburgh

  Preferred Date of Departure: 2014-12-20

  Preferred Data of Arrival: 2014-12-29

  Other Details / Notes: [any-text]
  ```

3. Login to [http://rhcs-travel-agency-demo.10.1.2.2.xip.io/business-central](http://rhcs-travel-agency-demo.10.1.2.2.xip.io/business-central)

  ```
  - login for admin role (u:erics / p:bpmsuite1!)
  ```

4. Two web services will be run and a sub-process to calculate the cost before deciding it is not needed that this booking be
	 reviewed on pricing, so you will find a task 'Employee Booking' for you to process.

5. Navigate to the "Tasks" tab -> "Task List" and click on it. 

6. Expand the right-side pane window.   Click on the "Work" tab and click on "claim" to claim the task.

7. Fill in the form provided for the task, it allows review of all the booking data submitted, generated by services and 
   calculated by the rules. You can request a review to send it back for a pricing review or check the completed box to 
   finish the task and process (isBookingConfirmed). All tasks have automated reassignment, meaning if not completed within 1 minute
   they will be put back into the group.

8. Enter credit card details (beginning with 1234...) for compensation to be triggered., Expiry details of the 
   card (e.g. 12/12) and your full name.

9. Check the logs and you will see that the process has been compensated.

10. To trigger different path for successful booking of Flights, just change the 'Credit Card details' to use any 
    card number that does not begin with 1234....

11. For details on demoing the compensation aspects of the Travel Agency demo project, 
    see [docs/compensation-howto/README-COMPENSATION.md](docs/compensation-howto/README-COMPENSATION.md)


Supporting Articles
-------------------
- [7 Steps to Your First Process with JBoss BPM Suite Starter Kit](http://www.schabell.org/2015/08/7-steps-first-process-jboss-bpmsuite-starter-kit.html)

- [A Micro Services Migration Story with JBoss BPM Travel Agency](http://www.schabell.org/2015/05/micro-services-migration-story-with-jboss-bpm-travel-agency.html)

- [Online Free PEX Webinar - A Guide to Modern BPM Tools](http://www.schabell.org/2015/04/online-free-pex-webinar-guide-to-modern-bpm-tools.html)

- [Quickest Way into the Clouds with JBoss BPM Travel Agency](http://www.schabell.org/2015/02/into-clouds-with-jboss-bpm-travel-agency.html)

- [Webinar - How to Excite the Travel Industry with a BPM Story](http://www.schabell.org/2015/02/webinar-how-to-excite-travel-industry.html)

- [Slides from webinar - How to excite the travel industry with a BPM story](http://www.schabell.org/2015/02/slides-webinar-jboss-bpm-travel-agency.html)

- [How to fly with the JBoss BPM Travel Agency (video 4 of 4)](http://www.schabell.org/2015/02/how-to-fly-with-jboss-bpm-travel-agency-part4.html)

- [How to fly with the JBoss BPM Travel Agency (video 3 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency-part3.html)

- [How to fly with the JBoss BPM Travel Agency (video 2 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency-part2.html)

- [How to fly with the JBoss BPM Travel Agency (video 1 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency.html)

- [Jump Start Your Rules, Events, Planning and BPM Today](http://www.schabell.org/2014/12/jump-start-rules-events-planning-bpm-today.html)

- [3 Reasons You Need The New JBoss Travel Agency](http://www.schabell.org/2014/12/3-reasons-you-need-new-jboss-travel-agency.html)

- [How To Excite the Travel Industry With a BPM Story](http://www.schabell.org/2014/10/how-to-excite-travel-agencies-with-bpm-story.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v1.0 - JBoss BPM Suite 6.2.0-BZ-1299002 on JBoss EAP 6.4.4 with travel agency installed on Red Hat CDK using OpenShift Enterprise image. 

![OSE Pod](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/rhcs-travel-agency-pod.png?raw=true)

![OSE Build](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/rhcs-travel-agency-build.png?raw=true)

[![Video part 1](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/video-part-1.png?raw=true)](http://vimeo.com/ericschabell/rhcs-travel-agency-part-1)

[![Video part 2](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/video-part-2.png?raw=true)](http://vimeo.com/ericschabell/rhcs-travel-agency-part-2)

[![Video part 3](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/video-part-3.png?raw=true)](http://vimeo.com/ericschabell/rhcs-travel-agency-part-3)

[![Video part 3](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/video-part-4.png?raw=true)](http://vimeo.com/ericschabell/rhcs-travel-agency-part-4)

![Agency Process](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/agency-process.png?raw=true)

![Calculate Process](https://github.com/redhatdemocentral/rhcs-travel-agency-demo/blob/master/docs/demo-images/calculate-process.png?raw=true)

![Compensation](https://raw.githubusercontent.com/redhatdemocentral/rhcs-travel-agency-demo/master/docs/demo-images/compensation-process.png?raw=true)

![Special Trips UI Form](https://raw.githubusercontent.com/redhatdemocentral/rhcs-travel-agency-demo/master/docs/demo-images/SpecialTripsUIform.png)

![Started Process](https://raw.githubusercontent.com/redhatdemocentral/rhcs-travel-agency-demo/master/docs/demo-images/started-process.png)

