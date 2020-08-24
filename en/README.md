# intdash SDK for Python - Sample Codes

This is a collection of notebooks for executing the sample codes described in [intdash SDK for Python - Code samples](https://docs.intdash.jp/sdk/python/latest/guide/codesample.html).

## Preparation

### Installation

Install with the following command.

```
$ pip install intdash
```

### Create a client

Create a client using your edge account credentials (**edge token** or **username/password combination** ).

Edge token

```
  import intdash

  client = intdash.Client(
	  url = "https://example.intdash.jp",
	  edge_token = "your_token",
  )
```

Username/password

```
  import intdash

  client = intdash.Client(
      url = "https://hoge.intdash.jp",
      username = "your_username_here",
      password = "your_password_here",
  )
```

### Register signal definitions

In these sample codes, there are cases where the signal definitions (definitions for converting time series data to physical values) are used when retrieving time series data. See `0_create_signals` for details.

#### Type of signal definition used

| Case | Signal definition |
|---|---|
|1_save-acquisition-data| General sensor data type (*) → Float type |
|2_JSON-data-acquisition-using-signal| JSON type → Float type|
|3_realtime-streaming-execution-processing| General sensor data type → Float type |
|4_acquistion-image-data|None|
|5_create-measurement-markers|General sensor data type → Float type|

(*) The general sensor type is a data type unique to aptpod. In these sample codes, this data type is used for smartphone sensor data.

### Prepare applications

In these samples, our **Visual M2M** applications are used for data transmission and data visualization. For details, see the guide of each application.

- Data transmission: **Visual M2M Motion**
- Data visualization: **Visual M2M Data Visualizer**
