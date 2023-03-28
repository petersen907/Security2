# Configuring Palo Alto Firewall PA-440
To configure our Firewall we followed the following steps/instructions.
https://docs.paloaltonetworks.com/pan-os/10-1/pan-os-admin/url-filtering/configure-url-filtering
We used steps 1, 2, 5, 7, 10, 11, 12, 13.

## Create a URL Filtering profile.
* `Select Objects> Security> Profiles> URL Filtering>` and Add or modify a URL Filtering profile

![FilteringProfile](https://user-images.githubusercontent.com/55543355/228132118-84e0cde5-d6a2-47cb-9ff1-178e5c4013e3.jpg)

* `Select "Site Access" drop down menu` and set all categories to "block"
* `Select each individual category you wish to allow access to`

Example

![ExampleAllowedCategories](https://user-images.githubusercontent.com/55543355/228134348-adb7067d-cba1-4da3-850f-4354cbad88b9.jpg)

## Apply Filtering
* `Select Policies> Security` Then, select a Security policy rule to modify.
* `Actions Tab` Edit the profile setting
* `Profile Type: Profiles`
* `URL Filtering: Select your newly created profile`
* `Click "OK" to Save changes` and commit the configuration

![SecurityPolicyRule](https://user-images.githubusercontent.com/55543355/228134073-de802ab1-9e5e-48e3-b8a9-fa47da6d4808.jpg)

## Running
Use your web browser to test Whitelist

![WhitelistWorking](https://user-images.githubusercontent.com/55543355/228134150-9038087d-5e89-474a-95e8-50a56b7c69f0.jpg)
