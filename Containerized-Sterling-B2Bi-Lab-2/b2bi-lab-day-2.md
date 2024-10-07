# Containerized Sterling B2Bi Lab - Day 2

## **0. Check on Sterling B2Bi installation**
In this section of the lab, we check on the Sterling B2Bi installation that it completed successfully.

0.1 (login to Openshift)

0.2 (look at the different namespaces/projects - db2, mq, app - that were deployed)

0.3 (go to db2 and mq namespaces one at a time and look at running pods, services for each)

0.4 (go to app namespace and show running pods, secrets (show db credentials), services, routes)

0.5 (in routes, click on app route to bring it up on browser)

---

## **1. Log into Containerized Sterling B2Bi**

1.1. To access B2Bi, login to your cluster with your user credentials by browsing to the 'OpenShift web console'.

1.2. From the administrator section menu on the left, click on the 'Networking' drop down menu and click on 'Routes', and at the top of the dashboard, select the 'sterling-b2bi-dev01-app' project. 
<img width="1678" alt="Screenshot 2024-10-04 at 1 25 31 PM" src="https://github.com/user-attachments/assets/efa494a5-76cb-45e9-a240-7779148fad95">


1.3. Search for 'dashboard' in the filtering options. Select the location url to access the Sterling B2Bi dashboard.
<img width="1676" alt="Screenshot 2024-10-04 at 1 25 03 PM" src="https://github.com/user-attachments/assets/ead8c74a-edb4-4d16-a763-daafb0a382d6">

1.4. Log in to Sterling B2Bi using the provided credentials.
      
      username = admin
      password = password
<img width="1233" alt="Screenshot 2024-10-04 at 1 26 13 PM" src="https://github.com/user-attachments/assets/461ca52a-2252-488d-9650-64e16da2bf40">

### Verify running version of Sterling B2B Integrator

1.5. Navigate to the Support page, indicated by the <img width="27" alt="Screenshot 2024-10-04 at 4 24 31 PM" src="https://github.com/user-attachments/assets/b5fbd0a4-b9c3-430b-8d57-7e9cd6a7d6cb"> icon. 
<img width="1055" alt="Screenshot 2024-10-04 at 4 36 10 PM" src="https://github.com/user-attachments/assets/5e4660bf-3b87-4a2c-8f07-caea0286c23c">


1.6. Navigate to the bottom of the screen to identify the version of running version of Sterling B2Bi. 
<img width="208" alt="Screenshot 2024-10-04 at 4 36 39 PM" src="https://github.com/user-attachments/assets/77705f2d-fae3-40ff-bcb9-b3d170dea6e5">

---

## **2. Create a Business Process**

In this section of the lab, we will create and execute a sample business process in Sterling B2Bi.
### Import a Sample Business Process in Sterling B2Bi  
2.1. From the administration menu on the left, click the 'Deployment' drop down menu and click on the 'Resource Manager' drop down to select 'Import/Export'.
<img width="1046" alt="Screenshot 2024-10-04 at 1 29 38 PM" src="https://github.com/user-attachments/assets/177ae478-c717-4b47-b181-5e43545e39dd">

2.2. Next to 'Import Resources', select the 'Go!' icon. 
<img width="1223" alt="Screenshot 2024-10-04 at 1 30 10 PM" src="https://github.com/user-attachments/assets/c8497316-203e-497c-8fb8-3d698cf7c74d">

2.3. Import the 'Sample-BP-Demo-B2Bi-Import.xml' file into Sterling B2Bi to import the sample business process. 
      Passphrase = password 
<img width="1003" alt="Screenshot 2024-10-04 at 3 51 04 PM" src="https://github.com/user-attachments/assets/36e62bbf-2aa3-4a6c-9192-82ead1032528">

2.4. Select default options and finalize the import by selecting 'Finish' to complete the import of the new business process in Sterling B2Bi. 
<img width="818" alt="Screenshot 2024-10-04 at 3 52 58 PM" src="https://github.com/user-attachments/assets/eef91a68-20ba-4fef-b75f-9aeec57fe1f5">
### Execute the Sterling B2Bi Business Process with Sample Data 

2.5 From the administration section menu on the left, click the 'Business Processes' drop down menu and select 'Manager'. 
<img width="939" alt="Screenshot 2024-10-04 at 2 08 24 PM" src="https://github.com/user-attachments/assets/43576d42-9995-4c02-916d-fb9ee9ab2236">

2.6. Search for the Process Name 'Sample-BP-Demo' and select the 'Go!' icon to locate the business process. 
<img width="1269" alt="Screenshot 2024-10-04 at 3 56 25 PM" src="https://github.com/user-attachments/assets/1662894c-917f-44ff-ae68-833ccc98c17c">

2.7. Once directed to the next page, click on the green 'Execution Manager' icon.
<img width="606" alt="Screenshot 2024-10-04 at 3 57 11 PM" src="https://github.com/user-attachments/assets/975d310f-2248-44cf-b1dc-5967d906949e">

2.7. Once directed to the next page, click on the green 'Execute' icon, to execute the sample business process in Sterling B2Bi.
<img width="861" alt="Screenshot 2024-10-04 at 3 58 09 PM" src="https://github.com/user-attachments/assets/39182472-7851-4a10-bfc4-5cb55ffd3c35">

2.8. Upload the sample data file 'Sample-Data' and select 'Go!' to execute the business process using the sample data. 
<img width="700" alt="Screenshot 2024-10-04 at 4 00 27 PM" src="https://github.com/user-attachments/assets/4cefa26c-1e9a-4cc8-a210-91e129a3e12f">

2.9. Review the execution of the sample business process. Once the processing is complete, B2Bi will indicate a status of 'Success'. 
<img width="786" alt="Screenshot 2024-10-04 at 4 01 01 PM" src="https://github.com/user-attachments/assets/eece3654-8f04-42fc-b04d-55628e3886f7">


---

## **3. Self-heal**
In this section of the lab, we see how RedHat OpenShift performs self healing when a pod is deleted. 

3.1. To delete the pod, login to your cluster with your user credentials by browsing to the `OpenShift web console`.  

3.2. From the administrator section menu on the left, click on the `Workload` drop down menu and click on Pods, and at the top, select the `sterling-b2bi-dev01-app` project.  

3.3. Select one of the `s0-b2bi` pods to delete and end of the row, click the vertical dot menu and click delete. 

<img width="1407" alt="Delete-a-pod" src="../images/sterling-b2bi-app-pods.png">
      
After the pod is deleted, the pod is reinstantiated and processing work as part of the deployed Sterling B2B Integrator cluster.

    >💡 **NOTE**     
    > While the pod is being terminated a new pod is being created.
    > If you delete on one of the pods or it crashes Openshift will automatically create a new pod to replace the problem pod
      
![terminate](../images/sterling-b2bi-deleting-pod.png)

      
![pod-up](../images/sterling-b2bi-pod-initializing.png)

---

## **4. Automatically Scale a Pod**
In this section of the lab, we see how Horizontal Pod Autoscaling works in the OpenShift cluster.  We will see how the Sterling B2B Integrator instance can manually or dynamically scale based on the load on the system.  For this lab we will manually modify pod scaling in the OpenShift console.


### Increase the Replica to 2

4.1. Log into the OpenShift console if you have not already.

4.2 From the administrator section menu on the left, click on the Workload drop down menu and click on StatefulSets, and at the top, select the `sterling-b2bi-dev01-app` project.

4.3 Click on the `s0-b2bi-ac-server` StatefulSet(SS) to open the details page.  In the top menu of the SS select `YAML`

4.4 Do a <CTRL + F>  search for `replicas` to find where to edit and change `replicas` from line 902 to 2

```yaml
spec:
  replicas: 1     <--- change to 2
  ```

4.5 Click save and navigate to pods to observe the scaling

   ![scaleup](../images/ac-server-scaling.png)

---

## **5. Upgrade/Roll Back**
In this section of the lab, we see how you can upgrade with using helm.

Using the `helm upgrade` command we see how the upgrade process is shortend.

5.1. To upgrade the version, first go to the IBM Sterling Console application and check the current version, which is version `6.2.0.2`. 

![v-2](../images/sterling%20V6.2.0.2.png)


5.2. Now let's go back to our bastion servers and update the `values.yaml` :

```bash
cd /tmp
```

5.3. Find the name of your `values.yaml` file.  The file name will look like `myb2bi_values-<id>.yml`

```bash
ls
```


5.4.  Inside `myb2bi_values-<id>.yml`, find & set the tag from `6.2.0.2` to `6.2.0.3` and change `enabled` to false under `dataSetup`.  Your files should already be updated
```yaml
global:
...
image:
  repository: cp.icr.io/cp/ibm-b2bi/b2bi
  tag: 6.2.0.2                          <----change to 6.2.0.3   
...
dataSetup:
  enabled: true                         <----change to false
  upgrade: false    
```

5.5. Download the latest helm chart 
```bash
wget https://github.com/IBM/charts/raw/master/repo/ibm-helm/ibm-b2bi-prod-3.0.5.tgz
```

5.6. Start the upgrade
```bash
helm upgrade --timeout 120m0s -f /tmp/myb2bi_values-<id>.yml -n sterling-b2bi-dev01-app s0 /tmp/ibm-b2bi-prod-3.0.5.tgz
```

    >💡 **NOTE**     
    > You may see a warning:
    > "Kubernetes configuration file is group-readable. This is insecure. Location: /tmp/ocp/cluster/auth/kubeconfig"
    > This should not affect the upgrade

Once the output of the process says `STATUS: deployed` we can go back to the console and view the pods.

5.6. To verify the version, simply go to the Sterling app menu and click on the support button in the Sterling Console.**  

![newerversion](../images/sterling%20v6.2.0.3.png)

We can also verify by going back to our pods and clicking on one of them.  Scroll down to the Containers section and the container image the pod is running.

![container-image](../images/sterling-container-image-version.png)


---

## **6. Log back into upgraded version of Sterling**


---






