# Создание и компиляция проекта

Создание проекта:

>\> `cargo new project_name`

Эта команда создаёт древо каталогов:

```
<project_name>
  |_Cargo.toml          (описание проекта и зависимости)
  |_.git                (если git доступен)
  |_.gitignore          (если git доступен)
  |_src
    |_main.rs           (код "Hello world" приложения)
```

*Cargo.toml* описывает проект и его структуру:

```rust,edition2018,no_run,noplaypen
[package]
name = "project_name"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"

[dependencies]
<dependency1> = "<version1>"
<dependency2> = "<version2>"
...
```
Опционально он может содержать разделы профилей. По умолчанию доступны профили `dev` и `release`. Они могут быть переопределены, также можно добавить новые профили, например:

```rust,edition2018,no_run,noplaypen
[profile.dev]
opt-level = 1

[profile.release]
opt-level = 3
```

Чтобы скомпилировать проект, перейдите в директорию проекта, откройте терминал и введите команду:

>\> `cargo build`

Обратите внимание, что компоновщик не входит в состав Rust. Внешний компоновщик используется для создания вывода.

Команда создает *./target/debug* каталог, в котором сохраняются выходные данные (это может быть исполняемый файл или библиотека).

Команда `build` также создает *Cargo.lock*, который содержит точную версию зависимостей, используемых для сборки проекта. Cargo необходимо заблокировать версии, поскольку версии зависимостей в *Cargo.toml* не являются точными, а скорее указывают ожидаемую «версию совместимости», в то время как *Cargo.lock* указывает точную версию.

Также вы можете:

Скомпилировать и запустить приложение:

>\> `cargo run`

Быстро скомпилировать проект, без создания выходных файлов:

>\> `cargo check`

Скомпилировать релизную версию приложения в категорию target/release:

>\> `cargo build --release`

Сгенерировать HTML документацию из кода проекта:

>\> `cargo doc --open`

Отформатировать код проекта:

>\> `cargo fmt`

---

[Руководство][original] было переведено и дополнено специально для сообщества "**rust_lang_ru**".

Подпишись на нас в **[Telegram][telegram]** и **[YouTube][youtube]**!

[original]: https://github.com/stencillogic/Start-with-Rust-fast
[telegram]: http://tlinks.run/rust_lang_ru
[youtube]: https://www.youtube.com/channel/UCu413rnSfuSSOR3OsIThlZA
