# Statik
A simple static RecyclerView for Android in Kotlin

### TLDR;

Statik turns this boring DSL setup

``` Kotlin
statik {
    section {
        header {
            text = "Features"
            textAttribute {
                color = "#ff4081"
                sizeSP = resources.getDimension(R.dimen.text_20)
            }
        }
        row {
            primaryText = "Simple Text"
        }
        row {
            primaryText = "Simple 2 Lines"
            secondaryText = "Second"
        }
        row {
            primaryText = "2 Lines"
            secondaryText = "With Icon"
            iconRes = android.R.drawable.ic_menu_call
        }
        row {
            primaryText = "2 Lines"
            secondaryText = "With Text accessory"
            iconRes = android.R.drawable.ic_delete
            accessory {
                text = "Error"
                textAttribute {
                    color = "#dc0030"
                    gravity = Gravity.END
                }
            }
        }
        row {
            primaryText = "2 Lines"
            secondaryText = "With custom widget"
            iconRes = android.R.drawable.ic_btn_speak_now
            accessory {
                layoutRes = R.layout.widget_checkbox
                configuration = {
                    it.find<CheckBox>(android.R.id.checkbox).setOnCheckedChangeListener { _, checked ->
                        toast("Checked is $checked")
                    }
                }
            }
        }
        footer {
            text = "Footer"
            textAttribute {
                color = "#333333"
                sizeSP = resources.getDimension(R.dimen.text_18)
            }
        }
    }
    section {
        header {
            text = "Adjustable Header"
            textAttribute {
                color = "#999999"
                sizeSP = resources.getDimension(R.dimen.text_24)
            }
        }
        row {
            primaryText = "Adjustable Primary"
            primaryTextAttribute {
                color = resources.getColor(R.color.colorAccent).toHexColor()
            }
            secondaryText = "Adjustable Secondary"
            secondaryTextAttribute {
                color = resources.getColor(android.R.color.holo_orange_dark).toHexColor()
                sizeSP = resources.getDimension(R.dimen.text_22)
            }
        }
        row {
            primaryText = "Clickable row"
            secondaryText = "For toast"
            clickHandler = {
                toast("You did good!")
            }
        }
        footer {
            text = "Visit Google here >"
            textAttribute {
                gravity = Gravity.END
            }
            configuration = {
                it.find<View>(android.R.id.title).setOnClickListener {
                    openBrowser("https://google.com")
                }
            }
        }
    }
}
```

into this good-looking static list

![](docs/screenshots/features.png)

### Usage

<TBD>
