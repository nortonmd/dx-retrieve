# Salesforce DX

#### Retrieve Metadata Using Salesforce DX Command Line Internface

## Prerequisites
* [Download Salesforce DX](https://developer.salesforce.com/docs/atlas.en-us.208.0.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm)
* [Developer Edition](https://developer.salesforce.com) (enable Dev Hub)

## Common DX Flags

```
-d  Your DevHub Org
-a  Assign Org Alias
-u  Reference Org Alias
```

**Getting Help**
Add --help onto the end of any sfdx command

```
sfdx --help
```

**Commands**

```
sfdx force:doc:commands:list
```

## Let's Go

For this example we're going to use a simple Contest application we'll refer to as `contestforce`, which has been assembled into an unmanaged package in an org with the name "Contest App".

**[Create](force_project_create.md) a project**

```bash
$ cd workspace
$ sfdx force:project:create -n contestforce
$ cd contestforce
```
Update the sfdx-project.json configuration file and change the *orgName* value to something else.

**[Connect](force_auth_web_login.md) your Developer Edition (a.k.a. DevHub) Account**

```bash
$ sfdx force:auth:web:login -d -a DevHub 
```

**Now connect the org in which you have developed your package**

```bash
$ sfdx force:auth:web:login -a MyOrg 
```

**Retrieve the package**

With DX, development work is separated into modules.  These modules are similar to packages or libraries in Java and C#.  This compartmentalization makes code management much simpler.

As mentioned above, for the purpose of this demo lets use a package called "Contest App".

[Retrieve](force_mdapi_retrieve.md) the package contents into a local zipped file.

```
$ sfdx force:mdapi:retrieve -s -r ./mdapi -p "Contest App" -u MyOrg -w 10
```

Unzip the retrieved file and show the results.

```
$ cd mdapi
$ unzip unpacakged.zip
```

You now have the source components in Metadata API format.

[Convert](force_mdapi_convert.md) the metadata format to the new DX format and push that code to GitHub.

```
$ sfdx force:mdapi:convert -r mdapi/
```

The contestforce app is now located under the `force-app/main/default` folder in Salesforce DX format.  
You now have the option of adding it to version control.

