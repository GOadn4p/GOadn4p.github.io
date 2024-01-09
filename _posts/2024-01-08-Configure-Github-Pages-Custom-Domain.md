## Configuring custom domain with NameCheap and configuring GitHub Pages for Custom Domain

**1.** Buy domain

**2.** Head to Domain list click Manage:
![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/eb488974-757f-4936-9672-04cde6525ad6)
**3.** Head to Advanced DNS
![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/390b16fa-c884-4c42-a2c2-f0a9bf377f7f)

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
![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/129f10f6-3c0b-4cf7-ae34-c41c0ba79039)

- Use the following format for your CNAME record

| Type	| Host | Value | TTL |
|--|--|--|--|
| CNAME Record	| www | GOadn4p.github.io. | Automatic |


**8.** Confirm your final results looks like the following:
![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/94efde8f-a72e-44fa-954d-3b3fd868ec60)

**10.** Test with the Dig command
- A Records
`dig <Your-Domain> +noall +answer -t A`
- AAAA Records
`dig <Your-Domain> +noall +answer -t AAAA`

**11.** Head to your git hub repo and select settings.
![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/63f82c34-6356-43bc-a482-ab9c4fed36c7)

**12.** Navigate to Pages in the sidebar.
![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/14798345-f75e-4735-89b8-76829fa755fd)

**13.** Configure the Custom Domain Section to contain your new domain.

![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/d257924a-3288-4d1a-9e1f-05fd4f8b577e)

**14.** Allow it to do the DNS check (Give it a while this does fail a few times due to how long it takes).

**15.** Once this is complete you can verify the record has been made by navigating to your repo root directory, there should be a new file named CNAME

![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/1fa2da26-899a-4140-9c13-d6cb0d6f44a8)

**16.** Opening this you should see your domain.

![image](https://github.com/GOadn4p/Wiki-Sharing/assets/139599365/f1b56b40-c90f-4c8e-bbb5-31e1c36d2227)

**17.** Browse to your new domain you should now see your GitHub Pages.




ref
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain
- https://www.youtube.com/watch?v=dbgEWWBvIxY
