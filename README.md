## Challenge-03

### Scenario
* Lets continue to enhance the ds-challenge-02
* So far we have done consistent way of creating tooling and extensions. Let's take a step further by enhancing this to create consistent way to build, package, run the programs and also creating standardized end points

### Set Up + verification
* It's time to create standardized commands. You will create two commands in devfile.yaml
    * Create 1st command with id "Build" and label (1. Build the application) inside devfile to execute below command
      ```bash
      dotnet build
      ```
    * Create 2nd command with id "Run" and lable (2. Run the Application) inside devfile to execute below command
      ```bash
      dotnet run
      ```
    * Leverage the Resources section and find how you can create commands in devfile.yaml
* Creating Two Endpoints in "tools" container of the devfile
    * The "/Controllers/DsChallenge03Controller.cs" has two restful endpoints :         
        * localhost:5152/api/hello
        * localhost:5152/api/greet/#input
    * Create 1st endpoint for "/api/hello" [with name="greet-attendee"]
    * Create 2nd endpoint for the root "/" [with name=base-challenge]
    * Leverage the Resources section and find how you can create endpoints
* Once you complete the above, reload the devspaces [Click the Arrows symbol(><) in the Bottom Left corner to open a new menu] with option "Restart Workspace from Local Devfile".
![ ](docs/images/challenge03.reload.jpg)

* If things don't look OK, delete the workspace, update the devfile directly in source control and recreate the workspace


### Success Criteria
* Commands are created and can be invoked via the "Hamburger Icon --> Terminal --> Run Task --> Devfile --> Select #Commands"
* Endpoints (shown in the bottom left corner of the IDE) can be invoked when live coding is ON
* Invoking "base-challenge" endpoint displays an image of the "Developer Flow"
![ ](docs/images/challenge03.endpoint.jpg)

* Invoking "greet-attendee" endpoint (or executing below command in the terminal) displays a response "Hello, DevSpaces"
    ```bash
    curl localhost:5152/api/hello?name=DevSpaces
    ```
* Leverage your /tests/ space as much as you can for accuracy and validation!

### Resources
* https://devfile.io/docs/2.2.2/adding-commands
* https://devfile.io/docs/2.2.2/defining-endpoints
* https://devfile.io/docs/2.2.2/devfile-schema

### What did we learn?
* OpenShift DevSpaces reduces the Developers pain points. As a Developer, your life is getting simpler with the below
* Now we have consitent endpoints and commands. This makes iterative development faster (no more typing commands and or finding endpoints via code)
* The next developer will know exactly how things are done making it a much better experience
* One of the core functions of development is to Test & Debug code. In the next challenge, we will explore further features of the devfile and how to customize specific resources

