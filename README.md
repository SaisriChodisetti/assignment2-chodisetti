# assignment2-chodisetti

# Sai Sri Rama Lakshmi Chodisetti

###### Munnar

> Munnar is a hill station on **Western Ghats** mountains located in **India**. The winter months are by far the best time to visit Munnar since the weather is pleasant. The journey along the hill station is pleasing and beautiful.

***

# Directions from Maryville to Munnar
1. Maryville
2. Kansas
    1. Kansas Airport
    2. Terminal
3. Chicago
    1. Chicago International Airport
    2. Terminal
4. Kochi Internatinal Airport
5. Munnar through private bus

* Bag Packing
    * Rain Coats
    * Tropical Clothes
    * Sunglasses
    * Sunscreen
* Tour Guide
* Camera

**[Click Here for AboutMe](AboutMe.md)**

***
## Food I would recommend

If someone wants to know which food makes me happy and try the things which I do go and check the below table

|Food      |Location |Amount  |
|:--------:|:-------:|:------:|
|Lemon Rice|India    |10      |
|Biryani   |Hyderabad|40      |
|Kaju Barfi|Kakainda |30      |

***
## Quotes I adore
> Fear cuts deeper than swords - Author : **George R.R. Martin** <br><br>
> Truth can be stated in a thousand different ways, yet each one can be true – Author : **Swami Vivekananda**

***
## Algorithm - Code Fencing

Algorithm Explanation : <https://en.wikipedia.org/wiki/Suffix_array>

> In computer science, a suffix array is a sorted array of all suffixes of a string. It is a data structure used in, among others, full text indices, data compression algorithms, and the field of bibliometrics.

```
vector<int> pn(n), cn(n);
    for (int h = 0; (1 << h) < n; ++h) {
        for (int i = 0; i < n; i++) {
            pn[i] = p[i] - (1 << h);
            if (pn[i] < 0)
                pn[i] += n;
        }
        fill(cnt.begin(), cnt.begin() + classes, 0);
        for (int i = 0; i < n; i++)
            cnt[c[pn[i]]]++;
        for (int i = 1; i < classes; i++)
            cnt[i] += cnt[i-1];
        for (int i = n-1; i >= 0; i--)
            p[--cnt[c[pn[i]]]] = pn[i];
        cn[p[0]] = 0;
        classes = 1;
        for (int i = 1; i < n; i++) {
            pair<int, int> cur = {c[p[i]], c[(p[i] + (1 << h)) % n]};
            pair<int, int> prev = {c[p[i-1]], c[(p[i-1] + (1 << h)) % n]};
            if (cur != prev)
                ++classes;
            cn[p[i]] = classes - 1;
        }
        c.swap(cn);
    }
    return p;
}
```
Source code : <https://cp-algorithms.com/string/suffix-array.html>