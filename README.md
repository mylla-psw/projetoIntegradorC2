{
    "header": {
        "namespace": "Alexa.Presentation.APL",
        "name": "RenderDocument",
        "messageId": "2074a0a6-05f9-4460-a1bf-0a742449400c",
        "keys": {
            "channel": "visual",
            "isBlocking": true,
            "navigationType": "NONE"
        },
        "dialogRequestId": "7a75dc73-ada1-46d8-b96a-162a715d119e"
    },
    "payload": {
        "presentationToken": "amzn1.as-tt.v1.Domain:Application:Lists#TID#A39IVP3CX8I5VA_ea9599b20d7a4d5ab7c9a85e94afad4f_YW16bjEuYWNjb3VudC5BRjZPMzVCNlk2Mk03WDRSN1YzVjJaSkxPT0tRLVNIT1BQSU5HX0lURU0=",
        "timeoutType": "SHORT",
        "document": {
            "onMount": [],
            "settings": {
                "Back": {
                    "backstackArrayName": "backstackIds"
                }
            },
            "import": [
                {
                    "name": "alexa-layouts",
                    "version": "1.2.0"
                },
                {
                    "name": "alexa-viewport-profiles",
                    "version": "1.1.0"
                }
            ],
            "resources": [],
            "graphics": {},
            "type": "APL",
            "version": "1.4",
            "layouts": {
                "AlexaListsHeaderDetailsEdit": {
                    "parameters": [
                        {
                            "name": "headerTitle",
                            "type": "string"
                        },
                        {
                            "name": "headerSubtitle",
                            "type": "string"
                        },
                        {
                            "name": "theme",
                            "type": "string"
                        }
                    ],
                    "items": [
                        {
                            "grow": 1,
                            "alignItems": "${@viewportProfileCategory == @hubRound ? 'center' : 'start'}",
                            "shrink": 1,
                            "type": "Container",
                            "items": [
                                {
                                    "grow": 1,
                                    "color": "${theme != 'light' ? '@colorTextSecondary' : '@colorTextReversed'}",
                                    "shrink": 1,
                                    "textAlign": "${@viewportProfileCategory == @hubRound ? 'center' : 'left'}",
                                    "onSubmit": [
                                        "${listItemDataSource.listNameEditEvent}"
                                    ],
                                    "paddingRight": "${!headerAttributionText && !headerAttributionImage ? '@headerHorizontalMarginRight' : '@headerHorizontalPadding'}",
                                    "type": "EditText",
                                    "when": "${!(listItemDataSource.isDefaultList) && headerTitle && headerTitle != '' && @viewportProfile != @tvLandscapeOverlay && @viewportProfile != @tvLandscapeXLarge}",
                                    "paddingBottom": "@headerVerticalPaddingBottom",
                                    "width": "100%",
                                    "maxLines": 1,
                                    "style": "textStyleTitle",
                                    "id": "AlexaListsHeaderDetailsEdit",
                                    "paddingTop": "@headerVerticalPaddingTop",
                                    "text": "${listName}",
                                    "opacity": 0.01,
                                    "paddingLeft": "@headerHorizontalMarginLeft",
                                    "height": "100%"
                                },
                                {
                                    "grow": 1,
                                    "color": "${theme != 'light' ? '@colorTextSecondary' : '@colorTextReversed'}",
                                    "shrink": 1,
                                    "textAlign": "${@viewportProfileCategory == @hubRound ? 'center' : 'left'}",
                                    "onSubmit": [
                                        "${listItemDataSource.listNameEditEvent}"
                                    ],
                                    "type": "EditText",
                                    "when": "${!(listItemDataSource.isDefaultList) && headerTitle && headerTitle != '' && @viewportProfile == @tvLandscapeXLarge}",
                                    "width": "100%",
                                    "maxLines": 1,
                                    "style": "textStyleTitle",
                                    "fontSize": "2.5vh",
                                    "id": "AlexaListsHeaderDetailsEdit",
                                    "text": "${listName}",
                                    "opacity": 0.01,
                                    "height": "10vh"
                                }
                            ],
                            "justifyContent": "start"
                        }
                    ]
                },
                "AlexaShoppingTextList": {
                    "parameters": [
                        {
                            "default": "dark",
                            "name": "theme",
                            "description": "Colors will be switched depending on the specified theme (light/dark). Default to dark theme",
                            "type": "string"
                        },
                        {
                            "name": "headerTitle",
                            "description": "Primary text to render in header.",
                            "type": "string"
                        },
                        {
                            "default": false,
                            "name": "headerDivider",
                            "description": "Toggle to display the divider that appears at the bottom of header to help separate it from the content below. Default to false",
                            "type": "boolean"
                        },
                        {
                            "name": "listVersion",
                            "description": "the version number of list being displayed on the screen, need for dynamicIndexLists.",
                            "type": "number"
                        },
                        {
                            "name": "fireTvEditButton",
                            "description": "Edit button text for fireTv",
                            "type": "string"
                        },
                        {
                            "name": "fireTvDeleteButton",
                            "description": "Delete button text for fireTv",
                            "type": "string"
                        },
                        {
                            "default": false,
                            "name": "headerBackButton",
                            "description": "Toggle to display back button in header.  Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "name": "listType",
                            "description": "Toggle to display back button in header.  Defaults to false.",
                            "type": "string"
                        },
                        {
                            "name": "headerBackButtonAccessibilityLabel",
                            "description": "An accessibility label to describe the back button to customers who use a screen reader.",
                            "type": "string"
                        },
                        {
                            "default": {
                                "type": "Back:GoBack"
                            },
                            "name": "headerBackButtonCommand",
                            "description": "Command that is issued when back button is pressed.",
                            "type": "any"
                        },
                        {
                            "default": "transparent",
                            "name": "headerBackgroundColor",
                            "description": "Optional color value to use as background color for Header. Defaults to transparent.",
                            "type": "color"
                        },
                        {
                            "name": "backgroundColor",
                            "description": "Color value to use as background color for layout.",
                            "type": "color"
                        },
                        {
                            "name": "backgroundImageSource",
                            "description": "URL for background image source.",
                            "type": "string"
                        },
                        {
                            "name": "backgroundVideoSource",
                            "description": "URL for background video source.",
                            "type": "any"
                        },
                        {
                            "default": "best-fill",
                            "name": "backgroundScale",
                            "description": "Image/video scale to apply to background image/video. Defaults to best-fill.",
                            "type": "string"
                        },
                        {
                            "name": "backgroundAlign",
                            "description": "Image/video alignment to apply to background image/video. Defaults to center.",
                            "type": "string",
                            "align": "center"
                        },
                        {
                            "default": false,
                            "name": "backgroundBlur",
                            "description": "Toggle to apply background blur. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "backgroundColorOverlay",
                            "description": "Toggle to apply overlay scrim to background image/video. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "backgroundOverlayGradient",
                            "description": "Toggle to apply gradient to background image/video. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "backgroundVideoAutoPlay",
                            "description": "Toggle to autoplay background video(s). Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": "foreground",
                            "name": "backgroundVideoAudioTrack",
                            "description": "Audio track to play on. Defaults to foreground. EM can select foreground | background | none.",
                            "type": "string"
                        },
                        {
                            "default": false,
                            "name": "hideDivider",
                            "description": "Toggle to hide the divider that appears at the bottom of each item to help separate it from the content below. Default to false",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "hideOrdinal",
                            "description": "Toggle to hide ordinal in list item. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "name": "primaryAction",
                            "description": "The action that is triggered when the item is selected.",
                            "type": "any"
                        },
                        {
                            "default": false,
                            "name": "touchForward",
                            "description": "Toggle to switch between touch forward and voice forward. Defaults to false, voice forward",
                            "type": "boolean"
                        },
                        {
                            "name": "listItems",
                            "description": "Array of list item datasources to present in list.  See documentation on list item datasources for required data signature.",
                            "type": "any"
                        },
                        {
                            "name": "listId",
                            "description": "ID of the list to be rendered",
                            "type": "string"
                        }
                    ],
                    "items": [
                        {
                            "width": "100%",
                            "type": "Container",
                            "items": [
                                {
                                    "backgroundColor": "${backgroundColor}",
                                    "backgroundImageSource": "${backgroundImageSource}",
                                    "backgroundVideoSource": "${backgroundVideoSource}",
                                    "overlayGradient": "${backgroundOverlayGradient}",
                                    "backgroundBlur": "${backgroundBlur}",
                                    "videoAudioTrack": "${backgroundVideoAudioTrack}",
                                    "videoAutoPlay": "${backgroundVideoAutoPlay}",
                                    "colorOverlay": "${backgroundColorOverlay}",
                                    "type": "AlexaBackground",
                                    "backgroundAlign": "${backgroundAlign}",
                                    "backgroundScale": "${backgroundScale}"
                                },
                                {
                                    "width": "100%",
                                    "position": "absolute",
                                    "type": "Container",
                                    "when": "${@viewportProfileCategory != @hubRound}",
                                    "items": [
                                        {
                                            "headerBackgroundColor": "${headerBackgroundColor}",
                                            "theme": "${theme}",
                                            "headerBackButton": "${headerBackButton}",
                                            "headerBackButtonCommand": "${headerBackButtonCommand}",
                                            "type": "AlexaListsHeader",
                                            "headerBackButtonAccessibilityLabel": "${headerBackButtonAccessibilityLabel}",
                                            "headerTitle": "${headerTitle}",
                                            "headerDivider": "${headerDivider}"
                                        },
                                        {
                                            "grow": 1,
                                            "data": "${listItems}",
                                            "entities": [
                                                {
                                                    "id": "alexaShoppingListItems_entity",
                                                    "type": "Text",
                                                    "value": "alexaShoppingListItems"
                                                }
                                            ],
                                            "numbered": true,
                                            "width": "100%",
                                            "id": "${listId}",
                                            "type": "Sequence",
                                            "scrollDirection": "vertical",
                                            "items": [
                                                {
                                                    "bind": [
                                                        {
                                                            "name": "myIndex",
                                                            "value": "${index + 1}"
                                                        }
                                                    ],
                                                    "entities": "${listItemDataSource.alexaListItemContainerComponentEntities}",
                                                    "speech": "${data.karaokeSpeech}",
                                                    "id": "${data.token}",
                                                    "type": "Container",
                                                    "items": [
                                                        {
                                                            "touchForward": "${touchForward}",
                                                            "ordinalIndex": "${myIndex}",
                                                            "fireTvDeleteButton": "${fireTvDeleteButton}",
                                                            "primaryAction": "${listItemDataSource.renderFullScreenEvent}",
                                                            "item_id": "${data.token}",
                                                            "primaryText": "${data.primaryText}",
                                                            "alexaListId": "${data.listId}",
                                                            "fireTvEditButton": "${fireTvEditButton}",
                                                            "hideDivider": "${hideDivider}",
                                                            "theme": "${theme}",
                                                            "type": "${(listType != 'AMAZON_LIST') ? 'AlexaShoppingTextListItem' : 'AlexaTextListItem'}",
                                                            "hideOrdinal": "${hideOrdinal}"
                                                        }
                                                    ]
                                                }
                                            ]
                                        }
                                    ],
                                    "height": "100%"
                                },
                                {
                                    "item": [
                                        {
                                            "bind": [
                                                {
                                                    "name": "myIndex",
                                                    "value": "${index + 1}"
                                                }
                                            ],
                                            "speech": "${data.karaokeSpeech}",
                                            "entities": "${listItemDataSource.alexaListItemContainerComponentEntities}",
                                            "id": "${data.token}",
                                            "type": "Container",
                                            "items": [
                                                {
                                                    "touchForward": "${touchForward}",
                                                    "ordinalIndex": "${myIndex}",
                                                    "primaryAction": "${data.primaryAction ? data.primaryAction : primaryAction}",
                                                    "item_id": "${data.token}",
                                                    "primaryText": "${data.primaryText}",
                                                    "alexaListId": "${data.listId}",
                                                    "hideDivider": "${hideDivider}",
                                                    "type": "${(listType != 'AMAZON_LIST') ? 'AlexaShoppingTextListItem' : 'AlexaTextListItem'}",
                                                    "hideOrdinal": "${hideOrdinal}",
                                                    "fireTvDeleteButton": "${fireTvDeleteButton}",
                                                    "listVersion": "${data.listVersion}",
                                                    "fireTvEditButton": "${fireTvEditButton}",
                                                    "theme": "${theme}"
                                                }
                                            ],
                                            "direction": "column"
                                        }
                                    ],
                                    "grow": 1,
                                    "data": "${listItems}",
                                    "entities": [
                                        {
                                            "id": "alexaShoppingListItems_entity_hub",
                                            "type": "Text",
                                            "value": "alexaShoppingListItems"
                                        }
                                    ],
                                    "numbered": true,
                                    "width": "100%",
                                    "id": "${listId}",
                                    "position": "absolute",
                                    "type": "Sequence",
                                    "scrollDirection": "@textListScrollDirection",
                                    "when": "${@viewportProfileCategory == @hubRound}",
                                    "height": "100%"
                                }
                            ],
                            "height": "100%"
                        }
                    ]
                },
                "AlexaShoppingLists": {
                    "parameters": [
                        {
                            "default": "dark",
                            "name": "theme",
                            "description": "Colors will be switched depending on the specified theme (light/dark). Default to dark theme",
                            "type": "string"
                        },
                        {
                            "name": "headerTitle",
                            "description": "Primary text to render in header.",
                            "type": "string"
                        },
                        {
                            "default": false,
                            "name": "headerDivider",
                            "description": "Toggle to display the divider that appears at the bottom of header to help separate it from the content below. Default to false",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "headerBackButton",
                            "description": "Toggle to display back button in header.  Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "name": "headerBackButtonAccessibilityLabel",
                            "description": "An accessibility label to describe the back button to customers who use a screen reader.",
                            "type": "string"
                        },
                        {
                            "default": {
                                "type": "Back:GoBack"
                            },
                            "name": "headerBackButtonCommand",
                            "description": "Command that is issued when back button is pressed.",
                            "type": "any"
                        },
                        {
                            "default": "transparent",
                            "name": "headerBackgroundColor",
                            "description": "Optional color value to use as background color for Header. Defaults to transparent.",
                            "type": "color"
                        },
                        {
                            "name": "backgroundColor",
                            "description": "Color value to use as background color for layout.",
                            "type": "color"
                        },
                        {
                            "name": "backgroundImageSource",
                            "description": "URL for background image source.",
                            "type": "string"
                        },
                        {
                            "name": "backgroundVideoSource",
                            "description": "URL for background video source.",
                            "type": "any"
                        },
                        {
                            "default": "best-fill",
                            "name": "backgroundScale",
                            "description": "Image/video scale to apply to background image/video. Defaults to best-fill.",
                            "type": "string"
                        },
                        {
                            "name": "backgroundAlign",
                            "description": "Image/video alignment to apply to background image/video. Defaults to center.",
                            "type": "string",
                            "align": "center"
                        },
                        {
                            "default": false,
                            "name": "backgroundBlur",
                            "description": "Toggle to apply background blur. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "backgroundColorOverlay",
                            "description": "Toggle to apply overlay scrim to background image/video. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "backgroundOverlayGradient",
                            "description": "Toggle to apply gradient to background image/video. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "backgroundVideoAutoPlay",
                            "description": "Toggle to autoplay background video(s). Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": "foreground",
                            "name": "backgroundVideoAudioTrack",
                            "description": "Audio track to play on. Defaults to foreground. EM can select foreground | background | none.",
                            "type": "string"
                        },
                        {
                            "default": false,
                            "name": "hideDivider",
                            "description": "Toggle to hide the divider that appears at the bottom of each item to help separate it from the content below. Default to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "hideOrdinal",
                            "description": "Toggle to hide ordinal in list item. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "name": "primaryAction",
                            "description": "The action that is triggered when the item is selected.",
                            "type": "any"
                        },
                        {
                            "default": false,
                            "name": "touchForward",
                            "description": "Toggle to switch between touch forward and voice forward. Only works when listImagePrimacy is false or primary text is promoted. Defaults to false, voice forward",
                            "type": "boolean"
                        },
                        {
                            "name": "listItems",
                            "description": "Array of list item datasources to present in list.  See documentation on list item datasources for required data signature.",
                            "type": "any"
                        },
                        {
                            "name": "listId",
                            "description": "ID of the list to be rendered",
                            "type": "string"
                        },
                        {
                            "name": "emptyPrimaryText",
                            "description": "Primary empty state message",
                            "type": "string"
                        },
                        {
                            "name": "footerHintText",
                            "description": "Hint text to display in Footer.",
                            "type": "string"
                        },
                        {
                            "name": "listItemHorizontalCount",
                            "description": "The number of list items in one screen",
                            "type": "number"
                        }
                    ],
                    "items": [
                        {
                            "width": "100%",
                            "type": "Container",
                            "when": "${!listItems || listItems.length == 0 && @viewportProfile != @tvLandscapeXLarge}",
                            "items": [
                                {
                                    "backgroundColor": "${backgroundColor}",
                                    "backgroundImageSource": "${backgroundImageSource}",
                                    "backgroundVideoSource": "${backgroundVideoSource}",
                                    "headerBackgroundColor": "${headerBackgroundColor}",
                                    "footerHintText": "${footerHintText}",
                                    "primaryText": "${emptyPrimaryText}",
                                    "headerBackButton": "${headerBackButton}",
                                    "headerBackButtonCommand": "${headerBackButtonCommand}",
                                    "type": "AlexaHeadline",
                                    "headerBackButtonAccessibilityLabel": "${headerBackButtonAccessibilityLabel}",
                                    "backgroundAlign": "${backgroundAlign}",
                                    "backgroundScale": "${backgroundScale}",
                                    "backgroundVideoAudioTrack": "${backgroundVideoAudioTrack}",
                                    "backgroundOverlayGradient": "${backgroundOverlayGradient}",
                                    "backgroundColorOverlay": "${backgroundColorOverlay}",
                                    "entities": [
                                        {
                                            "id": "backstackLength",
                                            "type": "Text",
                                            "value": "${environment.extension.Back.backstack.length}"
                                        }
                                    ],
                                    "backgroundBlur": "${backgroundBlur}",
                                    "theme": "${theme}",
                                    "backgroundVideoAutoPlay": "${backgroundVideoAutoPlay}",
                                    "accessibilityLabel": "${emptyPrimaryText}",
                                    "headerTitle": "${headerTitle}",
                                    "headerDivider": "${headerDivider}"
                                },
                                {
                                    "headerBackgroundColor": "${headerBackgroundColor}",
                                    "theme": "${theme}",
                                    "headerBackButton": "${headerBackButton}",
                                    "headerBackButtonCommand": "${headerBackButtonCommand}",
                                    "type": "AlexaHeader",
                                    "headerBackButtonAccessibilityLabel": "${headerBackButtonAccessibilityLabel}",
                                    "headerTitle": "${headerTitle}",
                                    "headerDivider": "${headerDivider}"
                                }
                            ]
                        },
                        {
                            "width": "100%",
                            "id": "tvOverlayEmptyListScreen",
                            "type": "TouchWrapper",
                            "when": "${!listItems || listItems.length == 0 && @viewportProfile == @tvLandscapeXLarge}",
                            "items": [
                                {
                                    "backgroundColor": "${backgroundColor}",
                                    "backgroundImageSource": "${backgroundImageSource}",
                                    "backgroundVideoSource": "${backgroundVideoSource}",
                                    "headerBackgroundColor": "${headerBackgroundColor}",
                                    "footerHintText": "${footerHintText}",
                                    "primaryText": "${emptyPrimaryText}",
                                    "headerBackButton": "${headerBackButton}",
                                    "headerBackButtonCommand": "${headerBackButtonCommand}",
                                    "type": "AlexaHeadline",
                                    "headerBackButtonAccessibilityLabel": "${headerBackButtonAccessibilityLabel}",
                                    "backgroundAlign": "${backgroundAlign}",
                                    "backgroundScale": "${backgroundScale}",
                                    "backgroundVideoAudioTrack": "${backgroundVideoAudioTrack}",
                                    "backgroundOverlayGradient": "${backgroundOverlayGradient}",
                                    "backgroundColorOverlay": "${backgroundColorOverlay}",
                                    "entities": [
                                        {
                                            "id": "backstackLength",
                                            "type": "Text",
                                            "value": "${environment.extension.Back.backstack.length}"
                                        }
                                    ],
                                    "backgroundBlur": "${backgroundBlur}",
                                    "theme": "${theme}",
                                    "backgroundVideoAutoPlay": "${backgroundVideoAutoPlay}",
                                    "headerTitle": "${headerTitle}",
                                    "headerDivider": "${headerDivider}"
                                },
                                {
                                    "headerBackgroundColor": "${headerBackgroundColor}",
                                    "theme": "${theme}",
                                    "headerBackButton": "${headerBackButton}",
                                    "headerBackButtonCommand": "${headerBackButtonCommand}",
                                    "type": "AlexaHeader",
                                    "headerBackButtonAccessibilityLabel": "${headerBackButtonAccessibilityLabel}",
                                    "headerTitle": "${headerTitle}",
                                    "headerDivider": "${headerDivider}"
                                }
                            ]
                        },
                        {
                            "touchForward": "${touchForward}",
                            "backgroundImageSource": "${backgroundImageSource}",
                            "primaryAction": "${primaryAction}",
                            "headerBackgroundColor": "${headerBackgroundColor}",
                            "headerBackButton": "${headerBackButton}",
                            "headerBackButtonCommand": "${headerBackButtonCommand}",
                            "type": "AlexaShoppingTextList",
                            "headerBackButtonAccessibilityLabel": "${headerBackButtonAccessibilityLabel}",
                            "when": "${listItems && listItems.length > 0}",
                            "listId": "${listId}",
                            "backgroundVideoAudioTrack": "${backgroundVideoAudioTrack}",
                            "listItems": "${listItems}",
                            "theme": "${theme}",
                            "backgroundColor": "${backgroundColor}",
                            "backgroundVideoSource": "${backgroundVideoSource}",
                            "hideDivider": "${hideDivider}",
                            "backgroundAlign": "${backgroundAlign}",
                            "hideOrdinal": "${hideOrdinal}",
                            "backgroundScale": "${backgroundScale}",
                            "backgroundOverlayGradient": "${backgroundOverlayGradient}",
                            "backgroundColorOverlay": "${backgroundColorOverlay}",
                            "backgroundBlur": "${backgroundBlur}",
                            "backgroundVideoAutoPlay": "${backgroundVideoAutoPlay}",
                            "headerTitle": "${headerTitle}",
                            "headerDivider": "${headerDivider}"
                        }
                    ]
                },
                "AlexaListsHeader": {
                    "parameters": [
                        {
                            "default": "dark",
                            "name": "theme",
                            "description": "Colors will be switched depend on the specified theme (light/dark). Default to dark theme",
                            "type": "string"
                        },
                        {
                            "name": "headerTitle",
                            "description": "Primary text to render in header.",
                            "type": "string"
                        },
                        {
                            "name": "headerSubtitle",
                            "description": "Secondary text to render in header.",
                            "type": "string"
                        },
                        {
                            "name": "headerAttributionText",
                            "description": "Attribution text to render in header. Only shown when no headerAttributionImage is provided, and when headerAttributionPrimacy is true, or on a device that shows Title/Subtitle and Attribution.",
                            "type": "string"
                        },
                        {
                            "name": "headerAttributionImage",
                            "description": "URL for attribution image source. Only shown when headerAttributionPrimacy is true, or on a device that shows Title/Subtitle and Attribution.",
                            "type": "string"
                        },
                        {
                            "default": true,
                            "name": "headerAttributionPrimacy",
                            "description": "On devices that can only display one element due to screen size, Attribution is prioritized. Setting False displays Title/Subtitle.  Defaults to true.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "headerDivider",
                            "description": "Toggle to display the divider that appears at the bottom of header to help separate it from the content below. Default to false",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "headerBackButton",
                            "description": "Toggle to display back button in header. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "name": "headerBackButtonAccessibilityLabel",
                            "description": "An accessibility label to describe the back button to customers who use a screen reader.",
                            "type": "string"
                        },
                        {
                            "default": {
                                "arguments": [
                                    "goBack"
                                ],
                                "type": "SendEvent"
                            },
                            "name": "headerBackButtonCommand",
                            "description": "Command that is issued when back button is pressed.",
                            "type": "any"
                        },
                        {
                            "default": "transparent",
                            "name": "headerBackgroundColor",
                            "description": "Optional color value to use as background color for Header. Defaults to transparent.",
                            "type": "color"
                        }
                    ],
                    "items": [
                        {
                            "backgroundColor": "${headerBackgroundColor}",
                            "item": {
                                "paddingBottom": "@headerVerticalPadding",
                                "alignItems": "center",
                                "paddingRight": "@headerHorizontalMargin",
                                "width": "100%",
                                "paddingTop": "@headerVerticalPadding",
                                "type": "Container",
                                "paddingLeft": "@headerHorizontalMargin",
                                "items": [
                                    {
                                        "headerAttributionText": "${headerAttributionText}",
                                        "type": "AlexaHeaderAttribution",
                                        "when": "${headerAttributionPrimacy && (headerAttributionImage || headerAttributionText)}",
                                        "headerAttributionImage": "${headerAttributionImage}"
                                    },
                                    {
                                        "headerSubtitle": "${headerSubtitle}",
                                        "width": "${viewport.width - (@marginHorizontal*2)}",
                                        "theme": "${theme}",
                                        "type": "AlexaHeaderDetails",
                                        "when": "${!headerAttributionPrimacy && (headerTitle || headerSubtitle)}",
                                        "headerTitle": "${String.toUpperCase(headerTitle)}"
                                    }
                                ],
                                "justifyContent": "center",
                                "direction": "column"
                            },
                            "type": "Frame",
                            "when": "${@viewportProfileCategory == @hubRound}"
                        },
                        {
                            "backgroundColor": "${headerBackgroundColor}",
                            "item": {
                                "width": "100%",
                                "type": "Container",
                                "items": [
                                    {
                                        "alignItems": "start",
                                        "width": "100%",
                                        "type": "Container",
                                        "items": [
                                            {
                                                "paddingBottom": "@headerVerticalPaddingBottom",
                                                "paddingRight": "${!headerAttributionText && !headerAttributionImage ? '@headerHorizontalMarginRight' : '@headerHorizontalPadding'}",
                                                "headerSubtitle": "${headerSubtitle}",
                                                "theme": "${theme}",
                                                "paddingTop": "@headerVerticalPaddingTop",
                                                "type": "AlexaHeaderDetails",
                                                "accessibilityLabel": "${!listItemDataSource.isDefaultList ? '' : listName}",
                                                "paddingLeft": "@headerHorizontalMarginLeft",
                                                "headerTitle": "${listName}"
                                            },
                                            {
                                                "headerSubtitle": "${headerSubtitle}",
                                                "width": "100%",
                                                "theme": "${theme}",
                                                "position": "absolute",
                                                "type": "AlexaListsHeaderDetailsEdit",
                                                "headerTitle": "${listName}"
                                            },
                                            {
                                                "headerAttributionText": "${headerAttributionText}",
                                                "paddingRight": "@headerHorizontalMargin",
                                                "paddingTop": "${headerAttributionImage ? '@headerAttributionTopPadding' : '@headerVerticalPadding'}",
                                                "type": "AlexaHeaderAttribution",
                                                "when": "${(headerAttributionImage || headerAttributionText)}",
                                                "headerAttributionImage": "${headerAttributionImage}"
                                            }
                                        ],
                                        "justifyContent": "spaceBetween",
                                        "direction": "row"
                                    },
                                    {
                                        "item": {
                                            "primaryAction": "${headerBackButtonCommand}",
                                            "buttonStyle": "image",
                                            "theme": "${theme}",
                                            "type": "AlexaIconButton",
                                            "buttonSize": "@headerButtonSize",
                                            "vectorSource": "@backVectorSource",
                                            "accessibilityLabel": "${headerBackButtonAccessibilityLabel}"
                                        },
                                        "position": "absolute",
                                        "paddingTop": "@headerButtonTopPadding",
                                        "type": "Container",
                                        "when": "${headerBackButton && @viewportProfileCategory != @hubRound && @viewportProfileGroup != @tv}",
                                        "paddingLeft": "@headerButtonLeftPadding"
                                    },
                                    {
                                        "paddingRight": "@headerHorizontalMargin",
                                        "theme": "${theme}",
                                        "type": "AlexaDivider",
                                        "when": "${headerDivider && @viewportProfileCategory != @hubRound}",
                                        "paddingLeft": "@headerHorizontalMargin"
                                    }
                                ]
                            },
                            "type": "Frame"
                        }
                    ]
                },
                "AlexaShoppingDivider": {
                    "item": {
                        "item": {
                            "backgroundColor": "${theme == 'light' ? '@colorComponentReversed' : '@colorComponent'}",
                            "type": "Frame",
                            "opacity": 0.2,
                            "height": "${@viewportProfileCategory == @mobileLanscape ? @dividerHeight : 2dp}"
                        },
                        "paddingRight": "${@viewportProfile == @tvLandscapeOverlay ? 48dp : @listItemMarginRight}",
                        "width": "100%",
                        "type": "Container",
                        "paddingLeft": "${@viewportProfile == @tvLandscapeOverlay ? 48dp : @listItemMarginLeft}"
                    },
                    "parameters": [
                        {
                            "default": "dark",
                            "name": "theme",
                            "description": "Colors will be swiched depend on the specified theme (light/dark). Default to dark theme",
                            "type": "string"
                        }
                    ]
                },
                "AlexaShoppingTextListItem": {
                    "parameters": [
                        {
                            "default": "dark",
                            "name": "theme",
                            "description": "Colors will be switched depending on the specified theme (light/dark). Default to dark theme",
                            "type": "string"
                        },
                        {
                            "default": false,
                            "name": "hideOrdinal",
                            "description": "Toggle to hide ordinal in list item. Defaults to false.",
                            "type": "boolean"
                        },
                        {
                            "default": false,
                            "name": "hideDivider",
                            "description": "Toggle to hide the divider that appears at the bottom of each item to help separate it from the content below. Default to false",
                            "type": "boolean"
                        },
                        {
                            "name": "primaryText",
                            "description": "Primary text for each list item so that users can understand and select an item.",
                            "type": "string"
                        },
                        {
                            "name": "listVersion",
                            "description": "the version number of list being displayed on the screen, need for dynamicIndexLists.",
                            "type": "number"
                        },
                        {
                            "name": "fireTvDeleteButton",
                            "description": "Primary text for fire tv delete button.",
                            "type": "string"
                        },
                        {
                            "name": "fireTvEditButton",
                            "description": "Primary text for fire tv edit button",
                            "type": "string"
                        },
                        {
                            "name": "entities",
                            "description": "Entity objects to store information about items.",
                            "type": "any"
                        },
                        {
                            "name": "primaryAction",
                            "description": "The action that is triggered when the item is selected.",
                            "type": "any"
                        },
                        {
                            "default": false,
                            "name": "touchForward",
                            "description": "Toggle to switch between touch forward and voice forward. Defaults to false, voice forward",
                            "type": "boolean"
                        },
                        {
                            "name": "item_id",
                            "description": "Id of the item we are displaying",
                            "type": "string"
                        },
                        {
                            "name": "alexaListId",
                            "description": "ID of the list",
                            "type": "string"
                        },
                        {
                            "name": "ordinalIndex",
                            "description": "Workaround for the issue in which ordinal does not update when adding items.  Will add corresponding APL JIRA when I have it",
                            "type": "number"
                        }
                    ],
                    "items": [
                        {
                            "grow": 1,
                            "shrink": 1,
                            "inheritParentState": true,
                            "type": "Container",
                            "items": [
                                {
                                    "grow": 1,
                                    "shrink": 1,
                                    "inheritParentState": true,
                                    "type": "Container",
                                    "items": [
                                        {
                                            "grow": 1,
                                            "inheritParentState": true,
                                            "shrink": 1,
                                            "type": "TouchWrapper",
                                            "when": "${@viewportProfile != @tvLandscapeOverlay && @viewportProfile != @tvLandscapeXLarge}",
                                            "items": [
                                                {
                                                    "grow": 1,
                                                    "shrink": 1,
                                                    "inheritParentState": true,
                                                    "style": "${@viewportProfile == @tvLandscapeOverlay ? (theme == 'light' ? 'touchableTextListItemLight' : 'touchableTextListItemDark') : ''}",
                                                    "type": "Container",
                                                    "items": [
                                                        {
                                                            "grow": 1,
                                                            "shrink": 1,
                                                            "inheritParentState": true,
                                                            "paddingRight": "@listItemMarginRight",
                                                            "width": "100%",
                                                            "type": "Container",
                                                            "paddingLeft": "@listItemMarginLeft",
                                                            "items": [
                                                                {
                                                                    "grow": 1,
                                                                    "paddingBottom": "${touchForward ? '@listItemPaddingBottomTouchForward' : '@listItemPaddingBottomVoiceForward'}",
                                                                    "shrink": 1,
                                                                    "inheritParentState": true,
                                                                    "width": "100%",
                                                                    "paddingTop": "${touchForward ? '@listItemPaddingTopTouchForward' : '@listItemPaddingTopVoiceForward'}",
                                                                    "type": "Container",
                                                                    "items": [
                                                                        {
                                                                            "item": {
                                                                                "theme": "${theme}",
                                                                                "type": "AlexaOrdinal",
                                                                                "ordinalText": "${ordinalIndex}"
                                                                            },
                                                                            "alignItems": "center",
                                                                            "inheritParentState": true,
                                                                            "paddingRight": "@listItemOrdinalRightPadding",
                                                                            "type": "Container",
                                                                            "when": "${!hideOrdinal}",
                                                                            "direction": "row",
                                                                            "height": "${(touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) > @ordinalDiameter ? (touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) : @ordinalDiameter}"
                                                                        },
                                                                        {
                                                                            "grow": 1,
                                                                            "shrink": 1,
                                                                            "paddingTop": "${(touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) >= @ordinalDiameter ? '0' : (@ordinalDiameter - (touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward))/2}",
                                                                            "type": "Container",
                                                                            "items": [
                                                                                {
                                                                                    "grow": 1,
                                                                                    "color": "${theme == 'light' ? '@colorTextReversed' : '@colorText'}",
                                                                                    "shrink": 1,
                                                                                    "entities": [
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${primaryText}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${item_id}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${alexaListId}"
                                                                                        }
                                                                                    ],
                                                                                    "textAlign": "left",
                                                                                    "maxLines": 4,
                                                                                    "style": "${touchForward ? '@listItemFontStyleTouchForward' : '@listItemFontStyleVoiceForward'}",
                                                                                    "id": "alexaListItemComponent_${item_id}_Text",
                                                                                    "text": "${primaryText}",
                                                                                    "type": "Text"
                                                                                },
                                                                                {
                                                                                    "grow": 1,
                                                                                    "color": "${theme == 'light' ? '@colorTextReversed' : '@colorText'}",
                                                                                    "shrink": 1,
                                                                                    "textAlign": "left",
                                                                                    "onSubmit": [
                                                                                        "${listItemDataSource.itemUpdatedEvent}"
                                                                                    ],
                                                                                    "type": "EditText",
                                                                                    "entities": [
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${primaryText}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${item_id}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${alexaListId}"
                                                                                        }
                                                                                    ],
                                                                                    "width": "80vw",
                                                                                    "maxLines": 4,
                                                                                    "id": "alexaListItemComponent_${item_id}",
                                                                                    "position": "absolute",
                                                                                    "text": "${primaryText}",
                                                                                    "opacity": 0.01,
                                                                                    "height": "100%"
                                                                                }
                                                                            ]
                                                                        }
                                                                    ],
                                                                    "justifyContent": "start",
                                                                    "direction": "row"
                                                                }
                                                            ]
                                                        }
                                                    ],
                                                    "direction": "row"
                                                }
                                            ],
                                            "gestures": [
                                                {
                                                    "action": "slide",
                                                    "type": "SwipeAway",
                                                    "items": {
                                                        "backgroundColor": "#FAFAFA",
                                                        "width": "100%",
                                                        "type": "Frame",
                                                        "items": {
                                                            "textAlignVertical": "center",
                                                            "color": "black",
                                                            "textAlign": "right",
                                                            "paddingRight": "@marginHorizontal",
                                                            "width": "100%",
                                                            "fontSize": 60,
                                                            "text": "✓",
                                                            "type": "Text",
                                                            "height": "100%"
                                                        }
                                                    },
                                                    "onSwipeDone": "${listItemDataSource.itemSwipeEvent}",
                                                    "direction": "left"
                                                }
                                            ]
                                        },
                                        {
                                            "componentId": "itemParentTouchWrapper_${item_id}",
                                            "grow": 1,
                                            "shrink": 1,
                                            "type": "TouchWrapper",
                                            "when": "${@viewportProfile == @tvLandscapeXLarge}",
                                            "items": [
                                                {
                                                    "inheritParentState": true,
                                                    "style": "${@viewportProfile == @tvLandscapeOverlay ? (theme == 'light' ? 'touchableTextListItemLight' : 'touchableTextListItemDark') : ''}",
                                                    "type": "Container",
                                                    "items": [
                                                        {
                                                            "inheritParentState": true,
                                                            "paddingRight": "@listItemMarginRight",
                                                            "width": "100%",
                                                            "type": "Container",
                                                            "paddingLeft": "@listItemMarginLeft",
                                                            "items": [
                                                                {
                                                                    "paddingBottom": "${touchForward ? '@listItemPaddingBottomTouchForward' : '@listItemPaddingBottomVoiceForward'}",
                                                                    "inheritParentState": true,
                                                                    "width": "100%",
                                                                    "paddingTop": "${touchForward ? '@listItemPaddingTopTouchForward' : '@listItemPaddingTopVoiceForward'}",
                                                                    "type": "Container",
                                                                    "items": [
                                                                        {
                                                                            "item": {
                                                                                "theme": "${theme}",
                                                                                "type": "AlexaOrdinal",
                                                                                "ordinalText": "${ordinalIndex}"
                                                                            },
                                                                            "alignItems": "center",
                                                                            "inheritParentState": true,
                                                                            "paddingRight": "@listItemOrdinalRightPadding",
                                                                            "type": "Container",
                                                                            "when": "${!hideOrdinal}",
                                                                            "direction": "row",
                                                                            "height": "${(touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) > @ordinalDiameter ? (touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) : @ordinalDiameter}"
                                                                        },
                                                                        {
                                                                            "grow": 1,
                                                                            "shrink": 1,
                                                                            "paddingTop": "${(touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) >= @ordinalDiameter ? '0' : (@ordinalDiameter - (touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward))/2}",
                                                                            "type": "Container",
                                                                            "items": [
                                                                                {
                                                                                    "color": "${theme == 'light' ? '@colorTextReversed' : '@colorText'}",
                                                                                    "entities": [
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${primaryText}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${item_id}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${alexaListId}"
                                                                                        }
                                                                                    ],
                                                                                    "textAlign": "left",
                                                                                    "maxLines": 4,
                                                                                    "style": "textStyleDisplay6",
                                                                                    "id": "alexaListItemComponent_${item_id}_Text",
                                                                                    "text": "${primaryText}",
                                                                                    "type": "Text"
                                                                                },
                                                                                {
                                                                                    "inheritParentState": true,
                                                                                    "display": "none",
                                                                                    "width": "100%",
                                                                                    "id": "editTextContainer_${item_id}",
                                                                                    "position": "absolute",
                                                                                    "type": "Container",
                                                                                    "items": [
                                                                                        {
                                                                                            "grow": 1,
                                                                                            "color": "",
                                                                                            "textAlign": "left",
                                                                                            "onSubmit": [
                                                                                                "${listItemDataSource.itemUpdatedEvent}"
                                                                                            ],
                                                                                            "selectOnFocus": true,
                                                                                            "type": "EditText",
                                                                                            "highlightColor": "rgba(#FAFAFA, 0.15)",
                                                                                            "onBlur": [
                                                                                                {
                                                                                                    "componentId": "editTextContainer_${item_id}",
                                                                                                    "property": "display",
                                                                                                    "type": "SetValue",
                                                                                                    "value": "none"
                                                                                                }
                                                                                            ],
                                                                                            "entities": [
                                                                                                {
                                                                                                    "id": "${ordinalIndex}",
                                                                                                    "type": "Text",
                                                                                                    "value": "${primaryText}"
                                                                                                },
                                                                                                {
                                                                                                    "id": "${ordinalIndex}",
                                                                                                    "type": "Text",
                                                                                                    "value": "${item_id}"
                                                                                                },
                                                                                                {
                                                                                                    "id": "${ordinalIndex}",
                                                                                                    "type": "Text",
                                                                                                    "value": "${alexaListId}"
                                                                                                }
                                                                                            ],
                                                                                            "width": "100%",
                                                                                            "fontSize": "${@fontSizeLarge/2}",
                                                                                            "lineHeight": "@lineHeightLarge",
                                                                                            "id": "alexaListItemComponent_${item_id}",
                                                                                            "text": "${primaryText}",
                                                                                            "opacity": 1,
                                                                                            "fontWeight": "@fontWeightLight",
                                                                                            "height": "5vh"
                                                                                        }
                                                                                    ],
                                                                                    "height": "100%",
                                                                                    "direction": "row"
                                                                                }
                                                                            ]
                                                                        }
                                                                    ],
                                                                    "justifyContent": "start",
                                                                    "direction": "row"
                                                                }
                                                            ]
                                                        }
                                                    ],
                                                    "direction": "row"
                                                }
                                            ],
                                            "onFocus": [
                                                {
                                                    "componentId": "actionContainer_${item_id}",
                                                    "property": "display",
                                                    "type": "SetValue",
                                                    "value": "normal"
                                                },
                                                {
                                                    "componentId": "actionContainer_${listTemplateData[ordinalIndex-2].token}",
                                                    "property": "display",
                                                    "type": "SetValue",
                                                    "when": "${listTemplateData.length > 1}",
                                                    "value": "none"
                                                },
                                                {
                                                    "componentId": "actionContainer_${listTemplateData[ordinalIndex].token}",
                                                    "property": "display",
                                                    "type": "SetValue",
                                                    "value": "none"
                                                }
                                            ]
                                        },
                                        {
                                            "onPress": [
                                                "${listItemDataSource.renderFullScreenEvent}"
                                            ],
                                            "grow": 1,
                                            "shrink": 1,
                                            "type": "TouchWrapper",
                                            "when": "${@viewportProfile == @tvLandscapeOverlay}",
                                            "items": [
                                                {
                                                    "inheritParentState": true,
                                                    "style": "${@viewportProfile == @tvLandscapeOverlay ? (theme == 'light' ? 'touchableTextListItemLight' : 'touchableTextListItemDark') : ''}",
                                                    "type": "Container",
                                                    "items": [
                                                        {
                                                            "inheritParentState": true,
                                                            "paddingRight": 48,
                                                            "width": "100%",
                                                            "type": "Container",
                                                            "paddingLeft": 48,
                                                            "items": [
                                                                {
                                                                    "paddingBottom": "${touchForward ? '@listItemPaddingBottomTouchForward' : '@listItemPaddingBottomVoiceForward'}",
                                                                    "alignItems": "center",
                                                                    "inheritParentState": true,
                                                                    "width": "100%",
                                                                    "paddingTop": "${touchForward ? '@listItemPaddingTopTouchForward' : '@listItemPaddingTopVoiceForward'}",
                                                                    "type": "Container",
                                                                    "items": [
                                                                        {
                                                                            "item": {
                                                                                "theme": "${theme}",
                                                                                "type": "AlexaOrdinal",
                                                                                "ordinalText": "${ordinalIndex}"
                                                                            },
                                                                            "inheritParentState": true,
                                                                            "paddingRight": "@listItemOrdinalRightPadding",
                                                                            "type": "Container",
                                                                            "when": "${!hideOrdinal}",
                                                                            "height": "${(touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) > @ordinalDiameter ? (touchForward ? @listItemOrdinalContainerHeightTouchForward : @listItemOrdinalContainerHeightVoiceForward) : @ordinalDiameter}"
                                                                        },
                                                                        {
                                                                            "grow": 1,
                                                                            "shrink": 1,
                                                                            "type": "Container",
                                                                            "items": [
                                                                                {
                                                                                    "borderColor": "red",
                                                                                    "color": "${theme == 'light' ? '@colorTextReversed' : '@colorText'}",
                                                                                    "entities": [
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${primaryText}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${item_id}"
                                                                                        },
                                                                                        {
                                                                                            "id": "${ordinalIndex}",
                                                                                            "type": "Text",
                                                                                            "value": "${alexaListId}"
                                                                                        }
                                                                                    ],
                                                                                    "textAlign": "left",
                                                                                    "maxLines": 4,
                                                                                    "style": "textStyleDisplay6",
                                                                                    "id": "alexaListItemComponent_${item_id}",
                                                                                    "text": "${primaryText}",
                                                                                    "type": "Text"
                                                                                }
                                                                            ]
                                                                        }
                                                                    ],
                                                                    "justifyContent": "start",
                                                                    "direction": "row"
                                                                }
                                                            ]
                                                        }
                                                    ],
                                                    "direction": "row"
                                                }
                                            ]
                                        },
                                        {
                                            "inheritParentState": true,
                                            "paddingRight": "@listItemMarginLeft",
                                            "display": "none",
                                            "paddingTop": "2vh",
                                            "id": "actionContainer_${item_id}",
                                            "type": "Container",
                                            "when": "${@viewportProfile == @tvLandscapeXLarge}",
                                            "items": [
                                                {
                                                    "buttonText": "${fireTvEditButton}",
                                                    "componentId": "actionContainerEditButton_${item_id}",
                                                    "primaryAction": [
                                                        {
                                                            "type": "Sequential",
                                                            "commands": [
                                                                {
                                                                    "componentId": "editTextContainer_${item_id}",
                                                                    "property": "display",
                                                                    "type": "SetValue",
                                                                    "value": "normal"
                                                                },
                                                                {
                                                                    "componentId": "alexaListItemComponent_${item_id}",
                                                                    "type": "SetFocus"
                                                                }
                                                            ]
                                                        }
                                                    ],
                                                    "theme": "${theme}",
                                                    "type": "AlexaButton"
                                                },
                                                {
                                                    "buttonText": "${fireTvDeleteButton}",
                                                    "primaryAction": "${listItemDataSource.itemSwipeEvent}",
                                                    "theme": "${theme}",
                                                    "type": "AlexaButton"
                                                }
                                            ],
                                            "direction": "row"
                                        }
                                    ],
                                    "direction": "row"
                                },
                                {
                                    "theme": "${theme}",
                                    "type": "AlexaShoppingDivider",
                                    "when": "${!hideDivider}"
                                }
                            ]
                        }
                    ]
                }
            },
            "extensions": [
                {
                    "name": "Back",
                    "uri": "aplext:backstack:10"
                }
            ],
            "mainTemplate": {
                "parameters": [
                    "listItemDataSource",
                    "listTemplateData"
                ],
                "items": [
                    {
                        "backgroundColor": "${(@viewportProfileGroup != @tv) ? backgroundColorCode : listItemDataSource.background.fireTVBackgroundColor}",
                        "item": {
                            "backgroundImageSource": "${(@viewportProfileGroup != @tv) ?  backgroundUrl : ''}",
                            "footerHintText": "${listItemDataSource.listTemplateHintText}",
                            "emptyPrimaryText": "${listItemDataSource.listTemplateEmptyListText}",
                            "headerBackButton": "${listItemDataSource.backButtonIsVisible}",
                            "headerBackButtonCommand": {
                                "type": "Back:GoBack"
                            },
                            "type": "AlexaShoppingLists",
                            "listType": "${listItemDataSource.listType}",
                            "backgroundAlign": "${isHestiaBackground ? listItemDataSource.background.hestiaBackgroundAlign : listItemDataSource.background.backgroundAlign}",
                            "backgroundScale": "${isHestiaBackground ? listItemDataSource.background.hestiaBackgroundScale : listItemDataSource.background.backgroundScale}",
                            "listId": "${listItemDataSource.listId}",
                            "listItems": "${listTemplateData}",
                            "fireTvDeleteButton": "${listItemDataSource.fireTvDeleteButton}",
                            "entities": [
                                {
                                    "id": "backstackLength",
                                    "type": "Text",
                                    "value": "${environment.extension.Back.backstack.length}"
                                }
                            ],
                            "fireTvEditButton": "${listItemDataSource.fireTvEditButton}",
                            "theme": "dark",
                            "id": "alexaListBaseItemsComponentWithEntities",
                            "headerTitle": "${(listTemplateData && listTemplateData.length > 0) ? listItemDataSource.listTemplateHeader : ''}"
                        },
                        "bind": [
                            {
                                "name": "listName",
                                "type": "string",
                                "value": "${listItemDataSource.listTemplateHeader}"
                            },
                            {
                                "name": "isHestiaBackground",
                                "type": "boolean",
                                "value": "${listItemDataSource.isHestiaBackground}"
                            },
                            {
                                "name": "backgroundUrl",
                                "type": "string",
                                "value": "${listItemDataSource.isHestiaBackground ? listItemDataSource.background.hestiaBackgroundImageSource[@viewportProfile + viewport.dpi] : listItemDataSource.background.backgroundImageSource}"
                            },
                            {
                                "name": "backgroundColorCode",
                                "type": "string",
                                "value": "${listItemDataSource.isHestiaBackground ? listItemDataSource.background.hestiaBackgroundColor : listItemDataSource.background.backgroundColor}"
                            }
                        ],
                        "entities": "${listItemDataSource.alexaListItemsBaseComponentEntities}",
                        "width": "100%",
                        "id": "alexaListItemsBaseComponent",
                        "type": "Frame",
                        "height": "100%"
                    }
                ]
            },
            "theme": "dark",
            "styles": {},
            "commands": {}
        },
        "datasources": {
            "listTemplateData": {
                "listId": "YW16bjEuYWNjb3VudC5BRjZPMzVCNlk2Mk03WDRSN1YzVjJaSkxPT0tRLVNIT1BQSU5HX0lURU0=",
                "startIndex": 0,
                "maximumExclusiveIndex": 2,
                "type": "dynamicIndexList",
                "items": [
                    {
                        "listId": "YW16bjEuYWNjb3VudC5BRjZPMzVCNlk2Mk03WDRSN1YzVjJaSkxPT0tRLVNIT1BQSU5HX0lURU0=",
                        "listVersion": 0,
                        "primaryText": "Comprar creme",
                        "karaokeSpeech": "https://tinytts.amazon.com/3/7cf5d99b-a6da-11eb-ad1d-437fc19c5ec1-9ec79f/16/1619560689427/d937c8328fe4b6bbe17fd2ef766e275565ae996fb82861da047288efc9372d82/resource.mp3",
                        "token": "f9d5d846-bf6e-44f0-bc3e-3b800ef516eb"
                    },
                    {
                        "listId": "YW16bjEuYWNjb3VudC5BRjZPMzVCNlk2Mk03WDRSN1YzVjJaSkxPT0tRLVNIT1BQSU5HX0lURU0=",
                        "listVersion": 0,
                        "primaryText": "Comprar carro",
                        "karaokeSpeech": "https://tinytts.amazon.com/3/7cf5d99c-a6da-11eb-ad1d-437fc19c5ec1-2ba859/16/1619560689427/6ca17c1e52b415bdd1ed5ae33d7eee1c2ce976a5f882772fb8599f53a7ff2e82/resource.mp3",
                        "token": "7d1468bd-40c7-485e-9929-4c8a247d04b8"
                    }
                ],
                "minimumInclusiveIndex": 0
            },
            "catapultPayloadData": {},
            "listItemDataSource": {
                "alexaListItemContainerComponentEntities": [
                    {
                        "id": "toDoContent_${myIndex}",
                        "type": "ToDoContent",
                        "value": "${data.primaryText}"
                    },
                    {
                        "id": "listItemName_${myIndex}",
                        "type": "ItemName",
                        "value": "${data.primaryText}"
                    }
                ],
                "isHestiaBackground": true,
                "alexaListItemsBaseComponentEntities": [
                    {
                        "id": "isFullScreen",
                        "type": "Text",
                        "value": "${@viewportProfile != @tvLandscapeOverlay}"
                    },
                    {
                        "id": "ListName",
                        "type": "ListName",
                        "value": "${listName}"
                    },
                    {
                        "id": "listType",
                        "type": "Text",
                        "value": "${listItemDataSource.listType}"
                    },
                    {
                        "id": "isDefaultList",
                        "type": "Text",
                        "value": "${listItemDataSource.isDefaultList}"
                    },
                    {
                        "id": "addOnlyWishList",
                        "type": "Text",
                        "value": "${listItemDataSource.isAddOnlyWishList}"
                    },
                    {
                        "id": "isHestiaBackground",
                        "type": "Text",
                        "value": "${isHestiaBackground}"
                    }
                ],
                "listNameEditEvent": {
                    "arguments": [
                        "LIST_NAME_UPDATED",
                        "${event.source.text}",
                        "${listName}"
                    ],
                    "type": "SendEvent"
                },
                "itemUpdatedEvent": {
                    "arguments": [
                        "ITEM_UPDATED",
                        "${event.source.value}",
                        "${item_id}",
                        "${listItemDataSource.listTemplateHeader}",
                        "${listItemDataSource.listType}",
                        "${listItemDataSource.isDefaultList}",
                        "${listTemplateData}"
                    ],
                    "type": "SendEvent"
                },
                "renderFullScreenEvent": {
                    "arguments": [
                        "RENDER_FULL_SCREEN",
                        "${listItemDataSource.listTemplateHeader}",
                        "${listItemDataSource.listType}",
                        "${listItemDataSource.isDefaultList}",
                        "${listTemplateData}"
                    ],
                    "type": "SendEvent",
                    "when": "${@viewportProfile == @tvLandscapeOverlay}"
                },
                "backButtonIsVisible": false,
                "listType": "SHOPPING_LIST",
                "itemSwipeEvent": {
                    "arguments": [
                        "ITEM_DELETE",
                        "${ordinalIndex-1}",
                        "${item_id}",
                        "${listItemDataSource.listTemplateHeader}",
                        "${listItemDataSource.listType}",
                        "${listItemDataSource.isDefaultList}",
                        "${listTemplateData}"
                    ],
                    "type": "SendEvent"
                },
                "isDefaultList": true,
                "listId": "YW16bjEuYWNjb3VudC5BRjZPMzVCNlk2Mk03WDRSN1YzVjJaSkxPT0tRLVNIT1BQSU5HX0lURU0=",
                "listTemplateHeader": "lista de compras",
                "fireTvDeleteButton": "Excluir",
                "background": {
                    "hestiaBackgroundImageSource": {
                        "hub-landscape-medium213": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-medium/213/bg_shopping.png",
                        "hub-landscape-large160": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-large/160/bg_shopping.png",
                        "hub-landscape-large480": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-large/480/bg_shopping.png",
                        "hub-round-small213": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-round/213/bg_shopping.png",
                        "hub-landscape-small240": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-small/240/bg_shopping.png",
                        "hub-landscape-large240": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-large/240/bg_shopping.png",
                        "hub-landscape-small213": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-small/213/bg_shopping.png",
                        "hub-round-small320": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-round/320/bg_shopping.png",
                        "hub-landscape-small320": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-small/320/bg_shopping.png",
                        "hub-landscape-medium320": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-medium/320/bg_shopping.png",
                        "hub-landscape-large320": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-large/320/bg_shopping.png",
                        "hub-landscape-medium480": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-medium/480/bg_shopping.png",
                        "hub-landscape-medium160": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-medium/160/bg_shopping.png",
                        "hub-round-small240": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-round/240/bg_shopping.png",
                        "hub-landscape-medium240": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-medium/240/bg_shopping.png",
                        "hub-landscape-large213": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-large/213/bg_shopping.png",
                        "hub-round-small480": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-round/480/bg_shopping.png",
                        "hub-round-small160": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-round/160/bg_shopping.png",
                        "hub-landscape-small160": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-small/160/bg_shopping.png",
                        "hub-landscape-small480": "https://m.media-amazon.com/images/G/01/AlexaLists/Shopping/hub-landscape-small/480/bg_shopping.png"
                    },
                    "backgroundImageSource": "https://d25vdjj6kk718x.cloudfront.net/bishop/bg_shopping_01.jpg",
                    "backgroundColor": "#467D2E",
                    "hestiaBackgroundColor": "#386E50",
                    "fireTVBackgroundColor": "#232F3E",
                    "backgroundAlign": "right",
                    "hestiaBackgroundAlign": "center",
                    "backgroundScale": "fit",
                    "hestiaBackgroundScale": "none"
                },
                "fireTvEditButton": "Editar",
                "isAddOnlyWishList": false
            }
        },
        "supportedViewports": [
            {
                "mode": "HUB",
                "shape": "ROUND",
                "minWidth": 100,
                "maxWidth": 599,
                "minHeight": 100,
                "maxHeight": 599
            },
            {
                "mode": "HUB",
                "shape": "RECTANGLE",
                "minWidth": 960,
                "maxWidth": 1279,
                "minHeight": 100,
                "maxHeight": 599
            },
            {
                "mode": "HUB",
                "shape": "RECTANGLE",
                "minWidth": 960,
                "maxWidth": 1279,
                "minHeight": 600,
                "maxHeight": 959
            },
            {
                "mode": "HUB",
                "shape": "RECTANGLE",
                "minWidth": 1280,
                "maxWidth": 1920,
                "minHeight": 600,
                "maxHeight": 1279
            },
            {
                "mode": "HUB",
                "shape": "RECTANGLE",
                "minWidth": 960,
                "maxWidth": 1279,
                "minHeight": 1920,
                "maxHeight": 2560
            },
            {
                "mode": "HUB",
                "shape": "RECTANGLE",
                "minWidth": 1920,
                "maxWidth": 2560,
                "minHeight": 960,
                "maxHeight": 1279
            },
            {
                "mode": "TV",
                "shape": "RECTANGLE",
                "minWidth": 960,
                "maxWidth": 960,
                "minHeight": 540,
                "maxHeight": 540
            },
            {
                "mode": "TV",
                "shape": "RECTANGLE",
                "minWidth": 300,
                "maxWidth": 300,
                "minHeight": 540,
                "maxHeight": 540
            },
            {
                "mode": "TV",
                "shape": "RECTANGLE",
                "minWidth": 960,
                "maxWidth": 960,
                "minHeight": 200,
                "maxHeight": 200
            }
        ],
        "presentationSession": {
            "id": "",
            "skillId": "Domain:Application:Lists",
            "grantedExtensions": [
                {
                    "uri": "aplext:backstack:10"
                }
            ]
        }
    }
}
