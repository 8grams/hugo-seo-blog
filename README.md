# Highly SEO Optimized Blog Template. Built with Hugo

This is a template of blog with highly optimized SEO best practices. Feel free to use it as base template for your blog.

## Why Hugo

[Hugo](https://gohugo.io/) is simple and fast static site generator built with Go. It really fast and can generate thousand pages in seconds. The deployment is easy as well, you only need a reverse proxy that can serve static html files.

## Usage

Clone Repository

```
~$ git clone https://github.com/8grams/hugo-seo-blog.git
```

Install Dependencies

```
~$ npm install
```

Build static HTML Pages

```
~$ npm run build
```

You can find and deploy your static HTML files in `dist` directory.

### Using Docker

Use Dockerfile provided in the source code to build your own docker image

```
~$ docker build . -t blog
```

### Deployment

The easiest way to deploy is using Docker. It's configured to serve your blog on path `https://you-site.abc/blog`. Below is example using Kubernetes Ingress for deployment

```
---
apiVersion: v1
kind: Service
metadata:
  name: blog
  namespace: blog
  labels:
    app: blog
spec:
  selector:
    app: blog
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: blog
  namespace: blog
  labels:
    app: blog
  annotations:
    kubernetes.io/ingress.class: nginx
spec:
  rules:
    - host: your-site.abc
      http:
        paths:
          - path: /blog
            pathType: Prefix
            backend:
              service:
                name: blog
                port: 
                  number: 80
```

## Admin Page

This blog template also provide admin page to manage your articles. It uses [Netlify](https://www.netlify.com/) as deploment plaform and requires your blog to be hosted as public repository on GitHub.

1. Go to https://www.netlify.com/ and Sign Up
2. On Dashbaord Main Page, klik `Add new site` and integrate with GitHub.
3. Choose your repository as site's source
4. Enable Identity and set Git Gateway
5. Open your admin page on https://link-from-netlify.netlify.app/blog/admin

## License

MIT License