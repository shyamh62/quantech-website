### Summary of Your GoDaddy DNS Records:

1. **Delete** the old `A` record (`WebsiteBuilder Site`).
    
2. **Add 4 `A` Records:**
    
    - `@` → `185.199.108.153`
        
    - `@` → `185.199.109.153`
        
    - `@` → `185.199.110.153`
        
    - `@` → `185.199.111.153`
        
3. **Set 1 `CNAME` Record:**
    
    - `www` → `shyamh62.github.io`


### Update Custom Domain in GitHub Pages Settings

1. Navigate to your repository at **`[https://github.com/shyamh62/quantech-website](https://github.com/shyamh62/quantech-website)`**.
    
2. Click **Settings** (gear icon on the top repository menu).
    
3. In the left sidebar, click **Pages** (under the "Code and automation" section).
    
4. Under **Custom domain**, type:
    
    Plaintext
    
    ```
    quantechmu.com
    ```


### Update `_config.yml` in Your Local Vault

Since your site is moving from the subpath `/quantech-website/` to the root of your new custom domain (`[https://quantechmu.com/](https://quantechmu.com/)`), you must clear the `baseurl` and set the new `url`.

1. Open `_config.yml` in Obsidian (or via Terminal).
    
2. Add the `url` and `baseurl` fields:
    

YAML

```
url: "https://quantechmu.com"
baseurl: ""
```
