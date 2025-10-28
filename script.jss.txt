// Smooth scroll & year in footer
document.addEventListener('DOMContentLoaded', function () {
  // Smooth scroll for anchors (works in most browsers)
  document.querySelectorAll('a[href^="#"]').forEach(function (anchor) {
    anchor.addEventListener('click', function (e) {
      // If href is just "#" or empty, skip
      var target = this.getAttribute('href');
      if (!target || target === "#") return;
      // Prevent default and smooth scroll
      e.preventDefault();
      var el = document.querySelector(target);
      if (el) {
        el.scrollIntoView({ behavior: 'smooth', block: 'start' });
      }
    });
  });

  // Set current year in footer
  var y = new Date().getFullYear();
  var el = document.getElementById('year');
  if (el) el.textContent = y;
});