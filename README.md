# RVM for RedHat OpenShift

A customised version of RVM that uses the non-standard install locations and environment variables in use on the RedHat OpenShift service.

## Installing
  
    $ curl -L https://raw.github.com/xiy/rvm-openshift/master/binscripts/install-rvm-openshift.sh | bash -s

Because of the limitations in place on the OpenShift system, you cannot have RVM inserted as a bash function through ~/.bash_profile, so you'll need to run the following command any time you wish to use RVM through SSH access:
  
    $ source $OPENSHIFT_DATA_DIR/.rvm/scripts/rvm

## Using SSH with OpenShift

To SSH into your OpenShift app box, find your SSH connection details using the rhc tools gem:
  
    $ rhc-user-info -l <email> -p <password>

It should look something like the following:
  
    bf7ef3ac5@appname-namespace.rhcloud.com

Then use this info to SSH into your box:
  
    $ ssh bf7ef3ac5@appname-namespace.rhcloud.com
    $ <password> type...type...type...