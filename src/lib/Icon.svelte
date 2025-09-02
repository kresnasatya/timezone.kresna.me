<script>
import MoonIcon from '@icons/moon.svg?raw';
import SunIcon from '@icons/sun.svg?raw';

const mapIcons = new Map();

mapIcons.set('sun', SunIcon);
mapIcons.set('moon', MoonIcon);

    /**
     * @typedef {Object} Props
     * @property {string} [name]
     * @property {string} [time]
     * @property {string} [width]
     * @property {string} [height]
     * @property {string} [fill]
     * @property {string} [stroke]
     * @property {string} [strokeWidth]
     */

    /** @type {Props} */
    let {
        name = 'sun',
        time = 'unknown',
        width = '24',
        height = '24',
        fill = $bindable('none'),
        stroke = $bindable('currentColor'),
        strokeWidth = '2'
    } = $props();

switch (time) {
    case 'morning':
        fill = '#FFF9C4'; /* Light Yellow */
        stroke = '#333333'; /* Dark Gray */
        break;
    case 'afternoon':
        fill = '#FFEB3B'; /* Bright Yellow */
        stroke = '#212121'; /* Darker Gray */
        break;
    case 'evening':
        fill = '#4b0082'; /* Indigo for evening */
        stroke = '#dda0dd'; /* Purple for evening */
        break;
    case 'night':
        fill = '#000033'; /* Very dark blue for night */
        stroke = '#ffffff'; /* White for night text */
        break;
}
</script>

<span role="img" aria-label="{time} time" style="display: inline; --width: {width}px; --height: {height}px; --stroke-width: {strokeWidth};
    --stroke: {stroke}; --fill: {fill};">
    {@html mapIcons.get(name)}
</span>

<style>
    /* CSS modules */
    span :global(svg) {
        width: var(--width);
        height: var(--height);
        fill: var(--fill);
        stroke-width: var(--stroke-width);
        stroke: var(--stroke);
    }
</style>
