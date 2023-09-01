# bevy_pixel_perfect_zoom

### With:

![](assets/WithPixelate.gif)

### Without:

![](assets/WithoutPixelate.gif)

2D Pixel Perfect post-processing shader for bevy. Zoom in the image with a shader to let the nearest-neighbor interpolation keep your image pixelated.

This is my first rust crate, please be understanding.

Look at my game [HyperBlast](https://github.com/Arthur-Aillet/HyperBlast) using this crate to test the result.

## Installation

```
cargo add --git https://github.com/Arthur-Aillet/bevy_pixel_perfect_zoom
```

```rust
use bevy_pixel_perfect_zoom::{PixelPerfectZoomPlugin, PixelPerfectZoomSettings};

fn main() {
    App::new()
        // ...
        .add_plugins(PixelPerfectZoomPlugin)
        // ...
        .add_systems(Startup, setup);
}

pub fn setup(mut commands: Commands) {
    commands.spawn((
        PixelPerfectZoomSettings {
            // Intensity of the zoom
            intensity: 1.,
            // Position of the camera
            // Moving the camera using the transform of the camera cause jittering effect and not smooth transitions
            position: Vec2::new(0., 0.),
        },
    ));
}

```

## Bevy Support Table

| bevy | bevy_pixel_perfect_zoom |
| -- | -- |
| 0.11 | 0.1 |


## License

bevy_pixel_perfect_zoom use the [MIT](LICENSE.md) license

## Contributing

Pull request are always welcome!
