# Product Sentiment Analysit 

<p align="center">
    <img src="./blog-post/assets/app.gif"  style="margin:15px">
</p>

As you see, this web app allows a user to evaluate random brands by writing reviews. While writing, the user will see the sentiment score of his input updating in real-time, alongside a proposed 1 to 5 rating.

The user can then change the rating in case the suggested one does not reflect his views, and submit.

You can think of this as a crowd sourcing app of brand reviews, with a sentiment analysis model that suggests ratings that the user can tweak and adapt afterwards.

To build this application, we'll follow these steps:

- Collecting and scraping customer reviews data using `Selenium` and `Scrapy`
- Training a deep learning sentiment classifier on this data using `PyTorch`
- Building an interactive web app using `Dash`
- Setting a `REST API` and a `Postgres` database
- Dockerizing the app using `Docker Compose`
- Deploying to `AWS`

<hr>

## Project architecture 

### Run the app locally


To run this project locally using `Docker Compose` `run`: 

```
docker-compose build
docker-compose up
```
You can then access the dash app at [http://localhost:8050](http://localhost:8050)

### Development

If you want to contribute to this project and run each service independently:

#### Launch API

In order to launch the API, you will first need to run a local `postgres` db using `Docker`:

```
docker run --name postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=password -e POSTGRES_DB=postgres -p 5432:5432 -d postgres
```

Then you'll have to type the following commands:

```shell
cd src/api/
python app.py
```

#### Launch Dash app

In order to run the `dash` server to visualize the output:

```shell
cd src/dash/
python app.py
```
