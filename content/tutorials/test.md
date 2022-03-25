+++
title = "Test syntax"
description = "wow"
date = 2022-03-13
+++

```rust, linenos, linenostart=0
mod engine;
pub use engine::music::playsound;
pub use engine::objects::{Object, ObjectState};
pub use crossterm::{
    event::{Event, EventStream, KeyCode},
    terminal::{disable_raw_mode, enable_raw_mode},
    Result,
    style::{Color, ContentStyle, Stylize},
};

pub use std::{
    cell::{RefCell, RefMut},
    collections::HashMap,
    time, borrow::BorrowMut
};

#[derive(Clone, Debug)]
pub struct Game {
    pub canvas: Canvas,
    pub tick_speed: time::Duration,
    pub objects: HashMap<usize, RefCell<Object>>,
    pub obj_len: usize,
}

impl Game {
    pub fn new(canvas_x: usize, canvas_y: usize, tick_speed: u64, st: ContentStyle) -> Game {
        Game {
            canvas: Canvas::new(canvas_x, canvas_y, st),
            tick_speed: time::Duration::from_millis(tick_speed),
            objects: HashMap::new(),
            obj_len: 0,
        }
    }
}
```
