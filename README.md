# FLP_Server

This is a testing tool for getting code coverage to work on local testing.

Prerequisites:
- nodejs
- Git command line

Open the command prompt and navigate to a directory where you want to install the server

Execute the following command
```
git clone https://github.com/kovboyjder/ui5-server-code-coverage-example.git
```

then run 
```
npm install
```

To get it to work open the UI5.yaml file in an text editor and add your username and password for HID client 100 under the ui5-middleware-code-coverage-server section.

To run the server write the following command in the command line.
```
npm run serve
```

Now open chrome and use the following command http://localhost:8080/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-ui-debug=true to open Fiori

Once done with testing, open up the chrome debugger by pressing F12

Select the console tab and add the following snippet
```
$.ajax({
  type: "POST",
  url: 'http://localhost:3000/coverage/client',
  data: JSON.stringify(window.__coverage__),
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json'
}
});
```

To see the code coverage open the http://localhost:3000/coverage in a new tab.
