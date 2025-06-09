# 1031CS Website Implementation Checklist

## Pre-Implementation
- [ ] Backup current Squarespace site
- [ ] Test changes on staging/development environment first

## Implementation Steps
- [ ] Upload `global-styles.css` to Squarespace Assets
- [ ] Add CSS loader code to Settings > Advanced > Code Injection > Header
- [ ] Clear browser cache and test

## Testing Checklist

### Visual Consistency
- [ ] All pages use Montserrat font
- [ ] Colors match across all pages (navy: #002B45, gold: #A48D29)
- [ ] Button styles are consistent
- [ ] Hover effects work properly (gold glow on cards/buttons)

### Performance
- [ ] Only one font family loads (check Network tab)
- [ ] Page load times improved
- [ ] No console errors
- [ ] Animations are smooth

### Responsiveness
- [ ] Mobile breakpoint (768px) works correctly
- [ ] Text sizes scale appropriately
- [ ] Cards/buttons adapt to mobile screens
- [ ] No horizontal scrolling on mobile

### Accessibility
- [ ] Reduced motion preferences respected
- [ ] Color contrast maintains accessibility standards
- [ ] Focus states visible and functional

### Browser Testing
- [ ] Chrome
- [ ] Safari
- [ ] Firefox
- [ ] Edge
- [ ] Mobile browsers (iOS Safari, Chrome Mobile)

## Maintenance Notes
- Use CSS variables from `global-styles.css` for any new components
- Test changes across all pages before deploying
- Keep the global CSS file updated with any new styles
- Document any custom modifications

## Troubleshooting
If styles don't load:
1. Check CSS file path in loader script
2. Verify file uploaded correctly to Squarespace
3. Clear browser cache
4. Check for JavaScript errors in console
5. Ensure CSS variables are properly defined 