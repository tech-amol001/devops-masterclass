# Execute scripts (sh/ps) from the Jenkins jobs

## Lab-01: Execute a shell script using Jenkins job

### Step-01: Connect to your Jenkins server (EC2) over SSH/RDP

### Step-02: Create a sample bash script for our Jenkins job and Test it

- Create a new file in /tmp/ directory with a label sample_script.sh by running following command:

```
sudo vi /tmp/sample_script.sh

# press i button to go insert mode

# Add below script into the file
#!/bin/bash
echo "Hello World, hope you are enjoy learning Jenkins"

# Type :wq! to Save and Quit from the file
```

- List the created script file and check the its permission:

```
sudo ls -lrt

# In case you do not have the execute permissions on your script file, you've to update it

```

- Assign the execute permission to your sample_script.sh file

```
sudo chmod 755 /tmp/sample_script.sh

```

- Now, test the script output by running it

```
sudo sh /tmp/sample_script.sh

# You must see the echo msg
```

### Step-03: Execute the script with Jenkins job

- Create a new Jenkins Freestyle job.
- Name: ExecuteScriptJob
- Click on the **Build** tab, then click on **Add build step** and choose **Execute shell**.

```
/tmp/sample_script.sh

```

- **Apply** and **Save** >> **Build Now**
- Now navigate to the Console output section of your job execution to see the script execution results.
