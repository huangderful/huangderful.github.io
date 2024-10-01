# huangderful.github.io
Questions to answer:
1. On average, how many requests can ab complete in 10 seconds with all the power of two concurrency levels between 1 and 256 (i.e., 1, 2, 4, 8, 16, 32, 64, 128, 256)?
Command used: ab -n 100000 -c 1 -t 10 http://huangderful.github.io/ # with varying -c

1: 763
2: 1335
4: 2934
8: 4951
16: 8231
32: 11113
64: 10143
128: 13717
256: 10833

2. Why are there diminishing returns at higher concurrency levels?
Web server constraints: there is only so much memory and threads allowed for each process and once that cap is hit you don't get as much in return. Also network constraints on server and client side because you might hit bandwidth caps. Last thing I can think of are that the server may not allow that many connections at once to a given IP for load balancing purposes.
3. What’s the performance difference when requesting HTTP and HTTPS?

4. How can GitHub respond so quickly?
5. What is your site’s “Total Blocking Time” (TBT) according to PageSpeed Insights?