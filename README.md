 <h1>Smart UI Testing With Selenium Python</h1> 
 
 <img height="400" src="https://user-images.githubusercontent.com/126776938/232534498-27618de9-6625-437e-904f-e94fc0bf38b9.png">



<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Learn the how to get started with Smart UI testing with Selenium Python on the TestMu AI platform with SmartUI*

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample)


## Table of Contents:

* [Pre-requisites](#pre-requisites)
* [Running Your First Selenium Python Test](#running-your-first-selenium-python-test)
* [Setting Up GitHub App Integration With SmartUI](#setting-up-github-app-integration-with-smartui)

## Pre-requisites

1. In order to run your Smart UI tests with Selenium Python, you will need to set your TestMu AI username and access key in the environment variables. Click the **Access Key** button at the top-right of the Automation Dashboard to access it.

![Screenshot 2023-04-18 132921](https://user-images.githubusercontent.com/126776938/232711334-676f1895-d223-4ee2-9bff-d82837715520.png)




**Windows**

```js
set LT_USERNAME="YOUR_USERNAME" 
set LT_ACCESS_KEY="YOUR ACCESS KEY"
```

**macOS/Linux**

```js
export LT_USERNAME="YOUR_USERNAME" 
export LT_ACCESS_KEY="YOUR ACCESS KEY"
```

2. To create a `New Project` using the SmartUI Web Application, click the **New Project** button in the top-right corner of your dashboard. 

![Screenshot 2023-04-18 133652](https://user-images.githubusercontent.com/126776938/232756183-051fc7b4-f923-410c-8168-78e44597fdc7.png)

3. Fill in the specifications such as **Platform**, **Project Name**, **Approvers**, and **Tags** as per your requirement and click **Create Project**.

![Screenshot 2023-04-18 134121](https://user-images.githubusercontent.com/126776938/232714262-56ae0be3-3ba3-4ba3-8e82-2f063657fcaf.png)

4. Install `pip` and Python.

```
sudo apt install python-pip
sudo apt install python
```

5. The recommended way to run your tests would be in `virtualenv`. It will isolate the build from other setups you may have running and ensure that the tests run with the specified versions of the modules specified in the `requirements.txt` file.

```
pip install virtualenv
```

## Running Your First Selenium Python Test

1. To get started, clone the `Python-Selenium-Sample` Repository.

```
git clone https://github.com/LambdaTest/smartui-python-sample
```

2. Next, create and activate the virtual environment in the `Python-Selenium-Sample` folder.

```
virtualenv venv
source venv/bin/activate
```
3. Inside the `Python-Selenium-Sample` folder, export the `TestMu AI Credentials`. You can get these from your automation dashboard.

4. To run your first test, run the below given command.
```
python test.py
```

## Setting Up Github App Integration with SmartUI

### Steps 1: Integrate the your TestMu AI Account with GitHub App. 

You can integrate your TestMu AI account with the GiHub application in the following ways:

- Using OAuth

![github-app-landing-92ef6e152a7302cb9ab88f5034b9ec0c](https://user-images.githubusercontent.com/126776938/232715867-f375b4df-1bc9-4e88-8340-44e986be2e9a.png)

### Step 2: Select your GitHub repository 

Go to your GitHub repository where you want to configure your SmartUI project. Check out our GitHub sample [here](https://github.com/LambdaTest/smartui-node-sample).

### Step 3: Configure your test suite

Add the `Github` capability to your current test configuration:

```bash
const capabilities: {
  platform: "Windows 10",
  browserName: "chrome",
  version: "latest",
  "smartUI.project": "Smart UI sample test",
   github: {
    "url": "https://api.github.com/repos/OWNER/REPO/statuses/commitId", // Mandatory
    "owner": "{OWNER}",  //Optional
    "repo": "{REPO}",  //Optional
    "commit": "{commitId}" //Optional
   }
}
```

### Step 4: Setting up your CI configuration

Setting up your CI workflow to execute on GitHub. Here is an example setup with `GitHub Actions`:

Go to `.github/workflows/<your_ci_file>.yml`.

```bash
    name: Execute SmartUI Test with Github App Integration
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1

    - name: Create commit status
      run: |
        API_HOST=https://api.github.com
        # Check out the PR branch
        git checkout $GITHUB_HEAD_REF
        # Get the commit ID of the last commit
        COMMIT_ID=$(git rev-parse HEAD)
        echo "Last commit ID of PR: $COMMIT_ID"
        GITHUB_URL=$API_HOST/repos/$GITHUB_REPOSITORY/statuses/$COMMIT_ID
        echo "GITHUB_URL: $GITHUB_URL"
        echo "GITHUB_URL=$GITHUB_URL" >> $GITHUB_ENV
```

### Step5: Execute your test suite with CI

After the setup is completed, you can now execute your test suite with the Continuos Integration (CI) pipeline with any tool of your choice.

### Step 6: Commit you changes over git on a branch and raise the PR to main branch.

### Step 7: Now you will see the `lambdatest-smartui-app` in the PR.


## Documentation & Resources :books:
      
Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample)
* [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample)    

## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/?utm_source=github&utm_medium=repo&utm_campaign=playwright-sample) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/)

## 🚀 LambdaTest is Now TestMu AI

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/) - we have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

### 🔄 Our Rebrand Journey

In 2017, we introduced LambdaTest with a clear mission: to become the world's most trusted cloud testing platform. We built a scalable, high-performance test cloud that eliminated flakiness, improved developer feedback cycles, and accelerated release velocity for teams worldwide.

As LambdaTest grew, we expanded the platform into Test Intelligence, Visual Regression Testing, Accessibility Testing, API Testing, and Performance Testing, covering the entire testing lifecycle. These capabilities enabled teams to test any stack, on any technology, at enterprise scale.

Over time, we rebuilt the architecture to be AI-native from the ground up. What began as LambdaTest's high-performance testing cloud has now evolved into TestMu AI, an AI-native, multi-agent platform redefining modern quality engineering.

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).

### 🔭 Explore TestMu AI

The same infrastructure LambdaTest customers relied on, now delivered through autonomous AI agents.

- [KaneAI](https://www.testmuai.com/kane-ai/)
- [Agent-to-Agent Testing](https://www.testmuai.com/agent-to-agent-testing/)
- [HyperExecute](https://www.testmuai.com/hyperexecute/)
- [Real Device Cloud](https://www.testmuai.com/real-device-cloud/)
- [Pricing](https://www.testmuai.com/pricing/)
- [Documentation](https://www.testmuai.com/support/docs/)