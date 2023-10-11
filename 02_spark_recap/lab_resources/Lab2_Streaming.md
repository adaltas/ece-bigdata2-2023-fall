# Spark Streaming

In this tutorial we are looking at a very simple Spark Streaming example. We are taking an example writen in a file which was provided with the installation. You can find description of it at and more detailed explanation of how Spark Streaming works on the following [website](https://spark.apache.org/docs/latest/streaming-programming-guide.html).

However let's first have a look at the script and analyse it.

1. In the spark or pyspark folder if you have installed it with pip go in the following folder `examples/src/main/python/streaming/` and open the file `network_wordcount.py` in your IDE and analyze the code.

2. Compare it with `wordcount.py` one folder up in `examples/src/main/python/`. What is the difference?

3. In the `network_wordcount.py` script, what does `ssc = StreamingContext(sc, 1)` and especially the argument `1` mean?

4. Explain this line of code:

    ```python
    lines = ssc.socketTextStream(sys.argv[1], int(sys.argv[2]))`
    ```

5. In your terminal, if you have Linux execute the command below and leave the it open:

    ```bash
    nc -lk 9999
    ```

    If you have Windows, you may install ncat and follow the procedures to run as explained on the foolowing [website](https://serverspace.io/support/help/how-to-install-ncat-tool-on_windows-and-linux/).

6. In another terminal execute the `network_wordcount.py` script with spark-submit in the pyspark folder as follows:

    ```bash
    ./bin/spark-submit examples/src/main/python/streaming/network_wordcount.py localhost 9999
    ```

7. In this command, what are `localhost` and `9999`?

8. In the terminal where you have ncat type any text you like and then have a look at the logs in the other terminal.

9. In your browser, have a look at the jobs, execution plans and dags in Spark UI with by default located at (http://localhost:4040), otherwise the IP address and port are indicated in the terminal where you have launched spark.

10. As Spark streaming is no longer being maintained and being replaced by `Spark Structured Streaming`

10. Do not forget to stop Spark Streaming and ncat when you have finished.
