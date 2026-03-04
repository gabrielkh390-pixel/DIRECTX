from kivy.app import App
from kivy.uix.widget import Widget
from kivy.graphics import Color, Rectangle
from kivy.core.window import Window

class MeuWidget(Widget):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        with self.canvas:
            Color(0, 0.6, 1, 1)  # Azul
            self.rect = Rectangle(pos=self.center, size=(200, 200))
        self.bind(pos=self.update_rect, size=self.update_rect)

    def update_rect(self, *args):
        self.rect.pos = (self.width/2 - 100, self.height/2 - 100)

class MeuApp(App):
    def build(self):
        Window.clearcolor = (0.1, 0.1, 0.1, 1)
        return MeuWidget()

if __name__ == "__main__":
    MeuApp().run()
