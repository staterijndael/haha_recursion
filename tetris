#include <iostream>
#include <SFML/Graphics.hpp>

using namespace std;
int main() {
	int M = 20, N = 10;

	int field[M][N] = { 0 };
	int w = 34;  // размер фигур

	struct Point {
		int x, y;

	}a[4], b[4];

	int figures[7][4] = {   // возможные расстановки фигур
		1, 3, 5, 7,
		2, 4, 5, 7,
		3, 5, 4, 6,
		3, 5, 4, 7,
		2, 3, 5, 7,
		3, 5, 7, 6,
		2, 3, 4, 5,

	};

	ios::sync_with_stdio(0);
	cin.tie(0);

	Texture t;
	t.loadFromFile("C:/Users/User21/Desktop/tiles.png");  // выгрузка изображения из файла

	Sprite tiles(t);  // создание спрайта
	tiles.setTextureRect(IntRect(0, 0, w, w)); // создание одной плитки

	RenderWindow window(VideoMode(N * w, M * w), "tetris");

	while (window.isOpen()) { 
		Event event;
		while (window.pollEvenr()) {
			if (event.type == Event::Close) {  // при закрытии окна игра заканчивается
				window.close;
			}
			int n = 4; // номер варианта 4 расположения фигур, типа в массиве figures

			for (int i = 0; i < 4; i++) {
				a[i].x = figures[n][i] % 2;
				a[i].y = figures[n][i] / 2;
			}

			window.Clear(Color::White); // создание игрового окна
			for (int i = 0; i < 4; i++) {  // вывод фигуры в игровое окно
				tiles.setPosition(a[i].x * w, a[i].y * w);
				window.draw(tiles);
			}

			window.display();
		}
	}
}
