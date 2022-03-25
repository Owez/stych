# Stytch Rust

Unofficial glue wrapper to use the basic email flow of Stytch inside of Rust

## Usage

```rust
use stytch::Stytch;

// store credentials
let stytch = Stytch::new(
    "project_id",
    "secret",
    "redirect_for_login",
    "redirect_for_signup"
);

// create new user
let user = stytch.login_or_create("root@ogriffiths.com").await?;

// authenticate
let authenticated = stytch.auth(user.token).await?;
if authenticated.is_ok() {
    println!("This user is good!");
} else {
    println!("Nope!");
}
```

## Why?

I needed to use Stytch as a requirement inside of an internal project, but there weren't any Rust adapters available. Feel free contribute or message me to take over this project as it's in maintenance mode as it stands!
