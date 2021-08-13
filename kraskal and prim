#include <bits/stdc++.h>

using namespace std;

typedef long long ll;
typedef long double ld;
typedef unsigned long long ull;

#define sort(a) sort(a.begin(), a.end())
#define PB push_back
#define PoB pop_back
const int INF = 1e9;
struct dsu {                        // это дсу для краскала
	vector<ll>par;
	vector<ll>size;

	dsu(ll n) {
		par.resize(n);
		size.resize(n, 1);
		for (ll i = 0; i < n; i++) {
			par[i] = i;
		}
	}
	ll get(ll v) {
		if (par[v] == v) {
			return v;
		}
		par[v] = get(par[v]);
		return par[v];
	}
	bool check(ll v, ll u) {
		return get(v) == get(u);
	}
	void _union(ll v, ll u) {
		v = get(v);
		u = get(u);
		if (size[v] > size[u]) {
			swap(u, v);
		}
		par[v] = u;
		size[u] += size[v];
	}
};
struct edge {
	ll u, v, w;
	edge(ll _u = 0, ll _v = 0, ll _w = 0) {
		u = _u;
		v = _v;
		w = _w;
	}
	bool operator<(edge e) const {
		return w < e.w;
	}
};
int main() {
	ios_base::sync_with_stdio(0);   // в мейне чисто алгоритм прима
	cin.tie(0);
	cout.tie(0);

	ll n, m;
	cin >> n >> m;

	vector<vector<pair<ll, ll>>> gr(n);

	for (ll i = 0; i < m; i++) {
		ll u, v, w;

		cin >> u >> v >> w;
		--u;
		--v;

		qr[u].PB({ v, w });
		gr[v].PB({ u, w });

	}
	vector < ll >d(n, INF);
	vector<bool>used(n, false);

	d[0] = 0;

	ll ans = 0;
	for (ll i = 0; i < n; i++) {
		ll v = -1;
		for (ll u = 0; u < n; u++) {
			if (!used[u] and (v == -1 or d[v] > d[u])) {
				v = u; 
			}
		}
		used[v] = true;
		ans += d[v];
		for (auto [u, w] : qr[v]) {
			if (d[u] > w) {                  
				d[u] = w;
			}
		}

	}
	cout << ans;

	return 0;            
}
