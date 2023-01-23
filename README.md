# Highly SEO Optimized Blog Template. Built with Hugo

This is a template of blog with highly optimized SEO best practices. Feel free to use it as base template for your blog.

## Why Hugo

Hugo is simple and fast static site generator built with Go. It really fast and can generate thousand pages in seconds. The deployment is easy as well, you only need a reverse proxy that can serve static html files.

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

The easiest way to deploy is using Docker. It's configured to serve your blog on path `https://you-site.abc/blog`.

## License

MIT License