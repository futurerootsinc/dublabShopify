# dublab Shopify Theme
Here we are maintaining dublab's online store codes

## Getting Started

Start by making a copy of the repository to your local environment.

```
git@github.com:futurerootsinc/dublabShopify.git
```

To deploy your code updates we use ThemeKit. To learn more visit [ThemeKit's website](https://shopify.github.io/themekit/).

The `master` branch is tracking the [production](https://secure.thetrackr.com/) website.

To add a new environment update the [config](https://github.com/TrackRbyPhoneHalo/TrackRShopify/blob/master/config.yml) file accordingly.
For example to create a new `test` environment add the following code to the bottom of the `config.yml` file.

```
test:
password: abc123
theme_id: "123"
store: mystore.myshopify.com
ignore_files:
	- config/settings_data.json
```

By default, git is ignoring the `setting_data.json` file but you have to **always** ignore it in the config file as well in order to avoid overwriting the data of the production.

## Workflow and Deployment

1. Always start your work by downloading the theme (just in case if the theme has been updated directly from the Shopify admin). **Changing files directly from the Shopify admin must be avoided.**

	```
	theme download --env production
	```

2. Create a new branch off of `master`.

3. Do work, commit and push changes to the remote branch frequently.

4. Push all the final changes up to origin for your branch.

5. Create a  [Pull Request in GitHub](https://help.github.com/articles/creating-a-pull-request/) and request a code review.

6. Upon code review approval, merge your branch to the `master`.

7. Deploy work via ThemeKit.
	```
	theme upload --env production
	```

