# ReversingLabs rl-secure TeamCity Examples

This repository contains a working example of a TeamCity project to illustrate scanning with the [ReversingLabs secure.software CLI](https://docs.secure.software/cli/). 

ReversingLabs secure.software CLI is capable of scanning [nearly any type](https://docs.secure.software/concepts/language-coverage) of software artifact or package that results from a build.

In this example, we're using the source code and Maven build instructions for the Struts2 showcase web app, which came with [Apache Struts v2.5.28](https://archive.apache.org/dist/struts/2.5.28/). 

The following example is provided in the `.teamcity` directory:

- **settings.kts**

To integrate the ReversingLabs secure.software CLI with TeamCity, follow the step-by-step [TeamCity integration guide](https://docs.secure.software/cli/integrations/teamcity).


## settings.kts

This is a TeamCity project settings file that defines two stages: **Build** and **RL scan**.
In the first stage, the WAR file is built and in the second stage, it is scanned with the CLI using the [ReversingLabs rl-scanner Docker image](https://hub.docker.com/r/reversinglabs/rl-scanner).

After the file is scanned, analysis reports in HTML, JSON, CycloneDX, and SPDX formats are saved in a ZIP file artifact. 

With each build, the HTML report is published under the `ReversingLabs Report` tab in TeamCity. 
