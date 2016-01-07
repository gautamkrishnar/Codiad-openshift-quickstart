# Codiad Web IDE on openshift

Codiad is a web-based IDE framework with a small footprint and minimal requirements. Codiad was built with simplicity in mind, allowing for fast, interactive development without the massive overhead of some of the larger desktop editors. That being said even users of IDE's such as Eclipse, NetBeans and Aptana are finding Codiad's simplicity to be a huge benefit. While simplicity was key, we didn't skimp on features and have a team of dedicated developer actively adding more. 

More information can be found at: http://codiad.com/

### Install with one click


Create an account at http://openshift.redhat.com/

[![Click to install OpenShift](http://launch-shifter.rhcloud.com/launch/light/Click to install.svg)](https://openshift.redhat.com/app/console/application_type/custom?&cartridges[]=php-5.4&initial_git_url=https://github.com/gautamkrishnar/Codiad-openshift-quickstart.git&name=codiad)

### How to use
After installing you can use codiad by pointing your browser to: http://codiad-yourdomain.rhcloud.com/

If you are experiencing any problems, please don't forget to open a [new issue](https://github.com/gautamkrishnar/Codiad-openshift-quickstart/issues/new) in this repository.

### Installing via the command line


Create a PHP application :

	rhc app create codiad php-5.4

You can also use any other custom name instead of 'codiad'. Remember to use that app name in the next command

Add this upstream grav quickstart repo

	cd codiad
	rm php/index.php
	git remote add upstream -m master git://github.com/gautamkrishnar/Codiad-openshift-quickstart.git
	git pull -s recursive -X theirs upstream master

Push the repo upstream to OpenShift

	git push        

Head to your application at:

	http://codiad-$yourdomain.rhcloud.com

To give your new codiad site a web address of its own, add your desired alias:

	rhc app add-alias -a codiad --alias "$whatever.$mydomain.com"

Then add a cname entry in your domain's dns configuration pointing your alias to $whatever-$yourdomain.rhcloud.com.

### Spread the word
Liked using Codiad Web IDE in openshift! Don't forget to spread the word by starring this repo.