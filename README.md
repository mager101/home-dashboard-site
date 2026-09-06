# home-dashboard-site

Two static pages that exist solely to satisfy Google's OAuth publishing
requirement. Google will not switch an External app from Testing to In
production without a reachable homepage URL and privacy policy URL, and
GitHub Pages needs a public repo on the free plan, which is why these live
here rather than in the private `home-dashboard` repo.

Nothing here describes the private setup. Do not add anything that does.

## Publish

```sh
git init
git add .
git commit -m "Add public pages for OAuth consent"
git branch -M main
git remote add origin https://github.com/mager101/home-dashboard-site.git
git push -u origin main
```

Create the repo on GitHub first, and make it **public**. Then in the repo:
Settings, Pages, Source "Deploy from a branch", branch `main`, folder `/ (root)`,
Save. The site appears at:

```
https://mager101.github.io/home-dashboard-site/
https://mager101.github.io/home-dashboard-site/privacy.html
```

First deploy takes a minute or two. Confirm both URLs load before continuing.

## Then, in Google Cloud Console

Google Auth Platform, Branding:

| Field | Value |
|---|---|
| Application home page | `https://mager101.github.io/home-dashboard-site/` |
| Application privacy policy link | `https://mager101.github.io/home-dashboard-site/privacy.html` |
| Authorised domains | `mager101.github.io` |

Leave the logo and Terms of Service empty. Uploading a logo forces you into
verification unless you stay in Testing, and the publish tooltip does not ask
for a Terms of Service.

Save, then go to Audience and click Publish app.

## About the contact address

The privacy policy points people at the support email shown on the consent
screen rather than printing an address, which keeps it off a public page that
scrapers read. If you would rather state it outright, edit the Contact section
of `privacy.html`.

## Accuracy

The privacy policy makes specific factual claims: read-only scope, no third
parties, no sharing, no model training, storage on your own machine. They are
true of the app as built. If that stops being true, change this page.
