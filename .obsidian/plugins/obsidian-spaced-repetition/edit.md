

### Task: Set the same definition for Hard than RESET 

- [ ] Change algorithm to be instant
- [x] Change SHortcuts? -- Doens't seem to work


```
 this._processReview(3 /* Reset */);
```

For resetting the button instructions:

```js
_createResetButton() {
    this.resetButton = this.controls.createEl("button");
    this.resetButton.addClasses(["sr-button", "sr-reset-button"]);
    (0, import_obsidian6.setIcon)(this.resetButton, "refresh-cw");
    this.resetButton.setAttribute("aria-label", t("RESET_CARD_PROGRESS"));
    this.resetButton.addEventListener("click", () => {
        this._processReview(3 /* Reset */);
});
```


Here a smaple using keydown


```
this.textArea.addEventListener("keydown", this.saveOnEnterCallback);
```

```js
this.saveOnEnterCallback = (evt) => {
    if ((evt.ctrlKey || evt.metaKey) && evt.key === "Enter") {
    evt.preventDefault();
    this.save();
    }
};
```



THis seems to be to edit the flashcard

```js

// src/gui/flashcard-review-view.tsx
var FlashcardReviewView = class {
  constructor(app, plugin, settings, reviewSequencer, reviewMode, contentEl, modalEl, backClickHandler, editClickHandler) {
    this._keydownHandler = (e2) => {
      if (document.activeElement.nodeName === "TEXTAREA" || this.mode === 3 /* Closed */) {
        return;
      }
      const consumeKeyEvent = () => {
        e2.preventDefault();
        e2.stopPropagation();
      };
      switch (e2.code) {
        case "KeyS":
          this._skipCurrentCard();
          consumeKeyEvent();
          break;
        case "Space":
          if (this.mode === 1 /* Front */) {
            this._showAnswer();
            consumeKeyEvent();
          } else if (this.mode === 2 /* Back */) {
            this._processReview(1 /* Good */);
            consumeKeyEvent();
          }
          break;
        case "Enter":
        case "NumpadEnter":
          if (this.mode !== 1 /* Front */) {
            break;
          }
          this._showAnswer();
          consumeKeyEvent();
          break;
        case "Numpad1":
        case "Digit1":
          if (this.mode !== 2 /* Back */) {
            break;
          }
          this._processReview(2 /* Hard */);
          consumeKeyEvent();
          break;
        case "Numpad2":
        case "Digit2":
          if (this.mode !== 2 /* Back */) {
            break;
          }
          this._processReview(1 /* Good */);
          consumeKeyEvent();
          break;
        case "Numpad3":
        case "Digit3":
          if (this.mode !== 2 /* Back */) {
            break;
          }
          this._processReview(0 /* Easy */);
          consumeKeyEvent();
          break;
        case "Numpad0":
        case "Digit0":
          if (this.mode !== 2 /* Back */) {
            break;
          }
          this._processReview(3 /* Reset */);
          consumeKeyEvent();
          break;
        default:
          break;
      }
    };
    this.app = app;
    this.plugin = plugin;
    this.settings = settings;
    this.reviewSequencer = reviewSequencer;
    this.reviewMode = reviewMode;
    this.backClickHandler = backClickHandler;
    this.editClickHandler = editClickHandler;
    this.modalContentEl = contentEl;
    this.modalEl = modalEl;
    this.chosenDeck = null;
    this.init();
  }
```

### MOdifying the Modal Width


```js

this.modalEl.style.width = this.settings.flashcardWidthPercentage + "%";
this.modalEl.style.maxWidth = this.settings.flashcardWidthPercentage + "%";
```

Adding some Textbox to all to draw?

```js

  _createHardButton() {
    this.hardButton = this.response.createEl("button");
    this.hardButton.addClasses([
      "sr-response-button",
      "sr-hard-button",
      "sr-bg-red",
      "sr-is-hidden"
    ]);
    this.hardButton.setText(this.settings.flashcardHardText);
    this.hardButton.addEventListener("click", () => {
      this._processReview(2 /* Hard */);
    });
  }


```

_createTextBox

_clearText|Box



Removing the colors

# I removed the following colors, to make it hidable


```


.sr-bg-green {
    background-color: #4caf50 !important;
}

.sr-bg-blue {
    background-color: #2094f3 !important;
}

.sr-bg-red {
    background-color: #ff7043 !important;
}

.sr-deck-list .sr-tree-item-row:hover .sr-bg-green,
.sr-response-button.sr-bg-green:hover {
    background-color: hsl(122, 39%, 44%) !important;
}

.sr-deck-list .sr-tree-item-row:hover .sr-bg-blue,
.sr-response-button.sr-bg-blue:hover {
    background-color: hsl(207, 90%, 49%) !important;
}

.sr-deck-list .sr-tree-item-row:hover .sr-bg-red,
.sr-response-button.sr-bg-red:hover {
    background-color: hsl(14, 100%, 58%) !important;
}


...

.sr-bg-blue,
.sr-bg-green,
.sr-bg-red {
    color: #000000 !important;
}

```
```
sr-header-stats-count
```




