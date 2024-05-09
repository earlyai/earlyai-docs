
## Setup and Configuration Guide


This Visual Studio Code extension is designed to automatically generate unit tests for TypeScript projects using Jest. Below is a guide to help you install, configure, and utilize the extension effectively.

**Prerequisites**
Before installing the extension, ensure you have the following prerequisites installed:
* NodeJS
* Jest
* TypeScript
* ts-jest
You can install Jest and TypeScript typings via npm:
```
npm install --save-dev jest @types/jest ts-jest
```
Supported Test Frameworks
* Jest: This extension is currently optimized for generating unit tests with Jest.
Installation
* Install the extension from the Visual Studio Code Marketplace.
* Ensure that your project is set up with NodeJS and Jest.
 
## Configuration

Configure Jest in your project to integrate with the extension. Below is an example of a typical Jest configuration suitable for TypeScript projects:
Filename is “jest.config.ts” and reside in the project root folder.

```import type { Config } from '@jest/types';
const config: Config.InitialOptions = {
  preset: 'ts-jest',
  testEnvironment: 'node',
  rootDir: 'src',
  testRegex: '.*\\.test\\.ts$',
  collectCoverageFrom: ['**/*.ts'],
  coverageDirectory: '../Coverage',
  moduleNameMapper: {
    "^@src/(.*)$": "<rootDir>/$1"
  }
};
export default config;
```
>Important Configuration Parameters:

* testEnvironment: Specifies the environment in which the tests are executed.
* collectCoverageFrom: Defines the files for which coverage information should be collected.
* coverageDirectory: Specifies the directory where coverage reports will be stored. Usually in the root folder.
* ModuleNameMapper: If you have path aliases in tsconfig.json, identify them under compilerOptions.paths. Then, add matching regex patterns to moduleNameMapper in your Jest config to mirror the aliases, using <rootDir> to map them to their corresponding directories, like this:
Ensure your Jest configuration is properly set up to work with TypeScript and the paths align with your project structure.
 
## Preparing to Use the Extension
Steps to Follow Before Generating Tests:
1.	Activate the Extension:
* Open your TypeScript project in Visual Studio Code.
* Switch to the extension's view.
2.	Verify Test Setup:
* Navigate to the test explorer in the extension's sidebar.
* Ensure you can successfully run existing tests. If tests do not run properly, you may need to adjust your Jest configuration according to the errors displayed in the [troubleshooting section].

## Setting Up Initial Tests:
If your project lacks any tests, begin by creating a basic test file:

* Place the test file in a directory included in the collectCoverageFrom array specified in your Jest configuration to ensure it contributes to the coverage report.
* Save the following content in a file named test/sample.early.test.ts within the test folder under your source directory:
```describe('Early Technologies Sample Tests', () => {
  it('Sample Test: Should validate true condition', () => {
    expect(true).toBeTruthy();
  });
});
```
 
## Using the Extension
To effectively use the extension for generating unit tests, follow these simple steps:
1.	Activate the Extension:
* Open your TypeScript project in Visual Studio Code.
* Switch to the extension's view.
2.	Locate the Target Method:
* Use the extension's sidebar to navigate the tree view and find the method or function you wish to test. Currently, only public methods can generate unit tests.
3.	Initiate Test Generation:
* You can generate unit tests in two ways:
a.	Click on the button next to the method name in the code explorer.
b.	Click on the "Generate tests" code-lens displayed above the public method name.
4.	Start the Test Generation Process:
* Press the 'play' button adjacent to the function or method in the tree view. This initiates the test generation.
5.	Monitor the Process:
* A popup window will appear at the bottom right of the IDE, indicating that the test generation is underway.
6.	Allow Time for Generation:
* The extension may take up to 60 seconds to automatically generate the necessary unit tests.
7.	Review the Generated Tests:
* Once the tests are generated, a new file containing the tests will be automatically added to your project.
 
## Troubleshooting
If you encounter any issues while using the extension, consider the following steps:

* If the Tree is not populated, reload the window.
* Verify Jest Configuration: Ensure that your Jest configuration matches your project setup, particularly ensuring that collectCoverage is set to true. The extension relies on Jest's coverage reports to function properly. If coverage is not being collected, the extension will not work as expected.
* Check Dependencies: Make sure that all dependencies, including Jest and @types/jest, are correctly installed and up to date.
* Check Extension Output: Monitor the "EarlyAI" output window within Visual Studio Code for feedback from the extension. This window displays specific error messages and diagnostics that can help identify any issues with the test generation process.

If the problem persists after these checks, please consider reporting the issue on the GitHub repository with detailed information about your setup and the errors encountered.

## Reporting Issues
If you encounter a bug or an issue, please report it via GitHub Issues:
1.	Visit the GitHub repository.
2.	Navigate to the 'Issues' section.
3.	Click on 'New Issue'.
4.	Provide a descriptive title and a detailed description of the issue. Attach screenshots or error logs, if possible, to help us understand the problem better.
5.	Submit the issue.
Suggesting Enhancements
We are always looking for ways to make our extension more useful:
1.	Visit the GitHub repository.
2.	Go to the 'Issues' section and check if a similar enhancement has already been proposed.
3.	If not, create a new issue by selecting the 'Feature request' template.
4.	Describe your idea with as many details as possible, explaining how it would benefit users of the extension.
5.	Submit the request.