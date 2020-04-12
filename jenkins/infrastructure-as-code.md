# Infrastructure as Code

## What is Infrastructure as code in the context of Jenkins

Jenkins understands groovy. Many routine jenkins jobs including builds can be written as a piece of groovy code. This code can well be saved in some SCM like Git and reused. This is a very powerful method to automate things in Jenkins. This technique of writing Jenkins jobs as piece of code is referred to as **Infrastructure as code**.
<br>

## What do we need
1. Jenkins up and running - on AWS instance or local instance
2. Install Groovy plug-in in Jenkins. **Manage Jenkins** > **Manage Plug-ins** > **Available** Tab > search for **Groovy** > Install and restart Jenkins as usual
3. Once the plug-in is installed, in **New Item** > **Build** section - Groovy option is available now

## Execute a simple groovy script inside Jenkins (without groovy plugin)
1. Go to **Manage Jenkins** > **Script Console**
2. Type your groovy script and execute
3. This could be used for testing purpose, but surely not more than that
4. You need admin permission to execute script this way, hence, not a recommended way

## Execute a simple groovy script inside Jenkins (with groovy plugin)
1. Now create a Freestyle project for the first time
2. Go to Build step
3. There are two options available - we will see their usage and use case at this point:
* Execute Groovy Script - They are recommended for usual purpose. These are executed outside the JVM which Jenkins uses. This used in controlling / orchestrating builds.
* Execute System Groovy Script - Needs elevated access. It can do few more things which a standard script cannot, due to elevated access. This uses the same VM that Jenkins uses. clearly, if anything that needs Jenkins own resources etc. we will go for this option. ** Jenkins admin** is allowed to run such scripts.
4. To be documented
