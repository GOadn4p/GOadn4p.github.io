## Configuring custom domain with NameCheap and configuring GitHub Pages for Custom Domain

**1.** Buy domain

**2.** Head to Domain list click Manage:

![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/b337999c-7874-4423-afb6-648e0f2bdb38)

**3.** Head to Advanced DNS
![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/b8b43bd2-0381-413c-9372-3bf57cc71741)

**4.** Add A Name records:

- The format for the A name records should be as follows:

| Type	| Host | Value | TTL |
|--|--|--|--|
| A Record| @ | 185.199.108.153 | Automatic |

- Add **4** _'A name'_ records, one for each of the following IPv4 addresses allocated by GitHub [Ref](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain).
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

- Add **4** _'A name'_ records, one for each of the following IPv6 addresses allocated by GitHub [Ref](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain).

```
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```
**5.** Add a 'CNAME' record for your GitHub Pages Repo:

- You can find your repo name at the top:

![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/4a9b318c-1a37-4d50-a5d9-af3b35afc5af)


- Use the following format for your CNAME record

| Type	| Host | Value | TTL |
|--|--|--|--|
| CNAME Record	| www | GOadn4p.github.io. | Automatic |


**8.** Confirm your final results looks like the following:
![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/6c99eb3c-afc3-4049-aec8-79bff4cc0560)

**10.** Test with the Dig command
- A Records
`dig <Your-Domain> +noall +answer -t A`
- AAAA Records
`dig <Your-Domain> +noall +answer -t AAAA`

**11.** Head to your git hub repo and select settings.
![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/5f166dcb-10bd-4d92-9fe3-36fe6011b8aa)

**12.** Navigate to Pages in the sidebar.

![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/df611cb4-04b4-4d93-9bde-1b48e0573e44)


**13.** Configure the Custom Domain Section to contain your new domain.

![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/925de8a1-08ef-4d59-b46b-42167f7cb9ef)


**14.** Allow it to do the DNS check (Give it a while this does fail a few times due to how long it takes).

**15.** Once this is complete you can verify the record has been made by navigating to your repo root directory, there should be a new file named CNAME

![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/e6bf7233-3ab9-46ff-aca6-b73b9054a68b)


**16.** Opening this you should see your domain.

![image](https://github.com/GOadn4p/GOadn4p.github.io/assets/139599365/11484c72-c2a0-45b4-b8b0-25372601b704)


**17.** Browse to your new domain you should now see your GitHub Pages.




ref
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain
- https://www.youtube.com/watch?v=dbgEWWBvIxY
