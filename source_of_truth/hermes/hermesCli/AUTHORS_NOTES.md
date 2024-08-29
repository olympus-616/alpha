# HermesCli - Progrommatic access to Olympus-616

## 0.1.x.x Hello World
This is a boiler plate scaffolding left as placeholder to indicate the need an desire to cli access to olympus-616

`
PS D:\dev\repos\olympus-616\olympus-616\source_of_truth\hermes\hermesCli> ./bin/dev hello Odysseus -f Olympus-616 
hello Odysseus from Olympus-616! (./src/commands/hello/index.ts)
`

## Roadmap
- Deploy HermesCli via NPM
- Create automated testing framework for HermesCli to ensure zero tech debt

## Notes on Testing this from Athena 8/27/24
To test your CLI tool, you’ll want to use a combination of unit tests, integration tests, and manual testing. Here’s a guide on how to set up and run tests for your CLI tool using popular tools and frameworks.

1. Set Up a Testing Framework:
First, ensure you have a testing framework installed. For TypeScript, Mocha and Chai are popular choices.

Install Mocha, Chai, and Sinon (for stubs, mocks, and spies):

bash
Copy code
npm install --save-dev mocha chai sinon
Install ts-node (for running TypeScript directly):

bash
Copy code
npm install --save-dev ts-node
Create a test Directory: This is where you’ll store your test files.

bash
Copy code
mkdir test
2. Write Unit Tests:
Create a Test File: Create a test file inside the test directory, for example, hello.test.ts:

bash
Copy code
touch test/hello.test.ts
Write a Basic Test: Here’s an example of a basic test for a command called hello:

typescript
Copy code
import { expect } from 'chai';
import { run } from '@oclif/test';

describe('hello command', () => {
  it('runs hello', () => {
    return run(['hello'])
      .then(ctx => {
        expect(ctx.stdout).to.contain('hello world');
      });
  });

  it('runs hello --name Homer', () => {
    return run(['hello', '--name', 'Homer'])
      .then(ctx => {
        expect(ctx.stdout).to.contain('hello Homer');
      });
  });
});
In this test, run is a utility provided by @oclif/test that allows you to simulate running your CLI command and then assert the output.

3. Add a Test Script to package.json:
Add the following script to your package.json to run the tests:

json
Copy code
"scripts": {
  "test": "mocha --require ts-node/register test/**/*.test.ts"
}
4. Run Your Tests:
Run the tests using npm:

bash
Copy code
npm test
This will execute your tests using Mocha, running any .test.ts files in the test directory.

5. Test Your CLI Tool Manually:
You can also manually test your CLI tool by running it directly from the command line:

Run the Command Locally:

If you haven't already, build the project:
bash
Copy code
npm run build
Run the CLI command:
bash
Copy code
./bin/dev <command> [options]
For example:
bash
Copy code
./bin/dev hello --name Homer
Test Different Scenarios:

Test edge cases and different command options.
Test how the tool handles incorrect inputs or missing arguments.
6. Continuous Integration (Optional):
If you're using a CI/CD pipeline (e.g., GitHub Actions, Travis CI), set up your configuration to run npm test as part of the build process. This will ensure that your CLI tool is automatically tested on every commit or pull request.

7. Debugging (Optional):
If you need to debug your CLI tool:

Use console.log: Simple but effective for printing out variables and states.
Use the VS Code Debugger:
Set breakpoints in your TypeScript files.
Run the tool using the VS Code debugger to step through the code.