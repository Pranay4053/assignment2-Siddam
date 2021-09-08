# assignment2-Siddam
# Sai Pranay Siddam
## Hyderabad
I like **Hyderabad** because its the best city lo live in **India** and best tourist **city**.

---

### Route Map

1. Go to MCI airport, Kansas city
2. Board into a flight to Rgia airport, India     
    1. Catch a ola/uber cab   
    2. Go the main city and enjoy tourist spots and food specially chicken biryani
* DSLR
* Selfiee Stick
* Power bank

[AboutMelink](AboutMe.md)

---
### Recommended Food

Below table shows the recommended food items and location , amount to be paid for their purchase.

|  Food Items    |    Location      |     Amount     |
|   ------       |    --------      |    --------    |
| Mutton Palav   |   Hyderabad      |      450       |
| Sambbar Idli   |   Chennai        |      200       |
| Keema Biryani  |   Bengalore      |      350       |
| Dal fry        |   Rajasthan      |      230       |

---

### Quotes

> Life is never fair, and perhaps it is a good thing for most of us that it is not - *Oscar Wilde*   
> Anyone who has never made a mistake has never tried anything new - *Albert Einstein*

---

### Shortest Paths

> In graph theory, the shortest path problem is the problem of finding a path between two vertices (or nodes) in a graph such that the sum of the weights of its constituent edges is minimized.The problem of finding the shortest path between two intersections on a road map may be modeled as a special case of the shortest path problem in graphs, where the vertices correspond to intersections and the edges correspond to road segments, each weighted by the length of the segment.      
(<https://en.wikipedia.org/wiki/Shortest_path_problem>)

```

const int INF = 1000000000;
vector<vector<pair<int, int>>> adj;

void dijkstra(int s, vector<int> & d, vector<int> & p) {
    int n = adj.size();
    d.assign(n, INF);
    p.assign(n, -1);
    vector<bool> u(n, false);

    d[s] = 0;
    for (int i = 0; i < n; i++) {
        int v = -1;
        for (int j = 0; j < n; j++) {
            if (!u[j] && (v == -1 || d[j] < d[v]))
                v = j;
        }

        if (d[v] == INF)
            break;

        u[v] = true;
        for (auto edge : adj[v]) {
            int to = edge.first;
            int len = edge.second;

            if (d[v] + len < d[to]) {
                d[to] = d[v] + len;
                p[to] = v;
            }
        }
    }
}

```
Link : (<https://cp-algorithms.com/graph/dijkstra.html>)





