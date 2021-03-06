# TST

TST is a set of command line tools used to create and test
programming assignments in introductory programming courses. TST
supports both input/output and script based tests. While TST is
primarily focused on python programming, we have successfully
used it for Java and Javascript (node.js) programming
assignments.

TST command line tools also serves as the CLI client for the TST
Online service --- a service that supports the cooperative study
and learn of programming.


## License

This software is licensed under the terms of the AGPL 3.0
license. Please read the LICENSE file.


## Documentation

To be written.


## Commands
**The command `tst --help` lists all the TST commands and `tst <command> --help` shows more details about an individual command**

Below, is a list with all TST commands and their descriptions.

### TST commands
Command | Description
------- | -----------
**checkout** | Download a TST question, create a shared object and a directory named with the question code received as argument.
**commit** | Send user response to TST server.
**login** | Login to a tst-online account using a token and the user email. Will open a page in the browser showing the required user token and email.
**ls** | List all TST availabe objects
**test** | Validate user answer using public tests.
**update** | Update TST to the latest stable release.

## Example
In this section we will see the process of login, resolve a TST question, test it and send to the server.

### Login
First you need to login to [TST-ONLINE](http://tst-online.appspot.com/). And then you can login to your account using:
```
$ tst login
```
Will open a new tab in the browser containing the token necessary for the login and the user TST-Online email. Copy the token and past in the terminal.

### Checkout
Copy the [TST](http://tst-online.appspot.com/#/) question checkout code and run the following command:

```sh
$ tst checkout <question_code>
```

After this you can go to the newly created directory that has been named with the question code and start coding your solution:

```sh
$ cd <question_code>
```

### Test
To test your solution, replace `<your_file_here>` with your program file and run:

```sh
$ tst test <your_file_here>
```
Or you can just run `tst` if there is only one `.py` file in the folder:

```sh
$ tst
```

If you received a output containing only points(e.g: `.`, `...`), you passed on public tests and now you can submit to the server.

### Send

Send your file to the server:

```sh
$ tst commit <your_file_here>
```

And then, you can verify if you passed in all tests and if your answer was accepted.

```sh
$ tst -s
```


## Dependencies

These scripts depend on Python 2.7 and on Bash. The scripts were
developed to be used primarily within a bash shell. While they
have been developed to be used in unix like environment in mind
(mostly Linux and OSX), some users have reported they were able
to use TST in Windows, using Cygwin.


## Installation

TST is a simple set of scripts. The commands below download and
run an interactive script that installs and configures tst. These
scripts are supposed to be run by the end user and not by root.
The scripts also assist the user to configure shell environment
variables and completion facilities to make tst more friendly.

### Latest release and pre-release

To install the latest stable release, run the following command.

    $ bash -c "$(curl -q -sSL http://bit.ly/tst-install)"

To install the latest development pre-release, first install
`tst` using the command above and update to the latest
pre-release (see below)

### Update

After tst is installed you can update your installation running
the `tst update` command to update to the latest stable release:

    $ tst update

Use the `--pre-release` option to update to the latest
development pre-release:

    $ tst update --pre-release

