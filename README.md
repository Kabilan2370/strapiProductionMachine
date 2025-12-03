<h2>Build the strapi application, build and develop it</h2>

<h4>To run and develop this strapi, we need at least 2cpu and 8GB ram. Othervise it will lag too much.</h4>

Here I used t3.large cpu and 8GB ram. I tried with t3.medium with 2 GB swap but It didn't work.
So, finally I choosed this instance type to run.

First install the nodejs on your machine and install the neccessary files.
Using the node install the "npm install -g yarn" because using this yarn we are going to build and develop the strapi.

Once I build the code I didn't start. I was confused then after enquired the issue the strapi project files is inside the
examples folder /strapi/emaples/getstarted/

We should run the "yarn develop" command inside the folder only. Otherwise it won't run. It will give the error only.
Now can access the <ip>:1337/admin
