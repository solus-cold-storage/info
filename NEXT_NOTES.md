
**General**

 - Richer UI
 - Animations

**Accessibility**

 - Budgie 11 needs to be completely accessible.
 - Current popovers break a11y, ensure all components are reusable and ATK registered

**Modular architecture**

 - All components being split up for Budgie 11
 - Raven = standalone, Panel = standalone, etc.

**Plugins**

 - All Widgets provided by Factory plugins.
 - Raven and Panel will use separate, versioned trees:
   - `$(libdir)/budgie-panel/11.0/plugins`
   - `$(libdir)/raven/11.0/plugins`
 - Individual plugins to be namespaced within each root:
   - `$(libdir)/budgie-panel/11.0/plugins/budgie-menu/*.so`
   - `$(libdir)/budgie-panel/11.0/plugins/budgie-menu/*.plugin`

**Raven**

 - Return to Widgets & Notifications only
 - Move Settings out completely
 - Resizable
 - Switch to drawer mode - i.e. overlap panels
 - Moving to out-of-process
 - Should support Widgets like:
    - RSS
    - Weather

**Panel**:

 - Multi-monitor
 - Panel per monitor
 - Drag reordering of widgets, with highlighting + animations.
 - Method to lockdown a panel.
 - Panels permitted on *any* edge.
 - Ensure panel never blocks window dragging between vertically arranged monitors.
 - Autohide abilities ("intellihide")
 - Variable width panels
 - Dock style mode for custom CSS class. Allow custom styling (or background occlusion) for dock mode Budgie panel.
 - Learn about newly installed Widgets dynamically

**Theming**

 - Arc Styling will move back into the arc-gtk-theme repo
 - 11 Styling to be different ?
 - Add a new "budgie-widget-factory" to `budgie-core` that can be run from git to facilitate simpler theme development.

**Widget Changes**

 - Sound Widget to merge into Panel Widget, and converted into optional Raven Widget

**Notifications:**

 - Richer notifications (Actionable)
 - Don't die with Rhythmbox. kthxbai.
 - Group the notifications by application
 - Raven needs a "Quiet Mode" (do not disturb)
 - Groups have a "last time", sort by this.
 - Dismiss on group basis too.

**Settings**:

 - Removed from Raven, need a new method in which to control these
 - "budgie-settings"
 - Replace GCC completely, even with the system control components
 - Use Windowed Mode for 11

**Terminology:**

 - Raven Applets to be known as "Raven Widgets"
 - Budgie Panel Applets = "Panel Widgets"
