# Remote typing tool

## Use case

The purpose of this software is to provide a means of showing text being typed on another screen.

## Usage

The software is simply a single HTML file that can be opened in any browser. By opening
the file in multiple windows, one of the windows can be chosen as the input while the others as output.

Any text typed on the input window will become visible on the output window.

The output window can be styled using CSS as needed.

## Implementation details

No server is required as long as all windows are opened on the same computer (and browser).

The different browser windows communicate using 
[local storage](https://developer.mozilla.org/en-US/docs/Web/API/Storage). The input window simply
adds the typed messages to storage. The output window listens to 
[storage events](https://developer.mozilla.org/en-US/docs/Web/API/StorageEvent) and updates the 
view on any changes.

Everything needed for running the tool is contained in a single file (index.html). So simply
store that file locally and open it in the browser, no web server required. Interestingly, local
storage also works for local files.
