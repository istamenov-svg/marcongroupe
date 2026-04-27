/* Marcon Groupe — site interactivity
   Persona tabs + mobile navigation toggle. No dependencies. */

(function () {
  'use strict';

  /* ---------- Persona tabs ---------- */
  var tabContainers = document.querySelectorAll('[data-persona-tabs]');

  tabContainers.forEach(function (container) {
    var buttons = container.querySelectorAll('.tab-button');
    var panes = container.querySelectorAll('.tab-pane');

    buttons.forEach(function (button) {
      button.addEventListener('click', function () {
        var target = button.getAttribute('data-tab');

        buttons.forEach(function (b) {
          b.classList.remove('is-active');
          b.setAttribute('aria-selected', 'false');
        });
        panes.forEach(function (p) {
          p.classList.remove('is-active');
        });

        button.classList.add('is-active');
        button.setAttribute('aria-selected', 'true');

        var pane = container.querySelector('.tab-pane[data-tab="' + target + '"]');
        if (pane) {
          pane.classList.add('is-active');
        }
      });
    });
  });

  /* ---------- Mobile nav toggle ---------- */
  var navToggle = document.querySelector('.nav-toggle');
  var nav = document.querySelector('.nav');

  if (navToggle && nav) {
    navToggle.addEventListener('click', function () {
      var isOpen = nav.classList.toggle('is-open');
      navToggle.setAttribute('aria-expanded', isOpen ? 'true' : 'false');
    });

    // Close mobile nav when a link is clicked
    nav.querySelectorAll('a').forEach(function (link) {
      link.addEventListener('click', function () {
        nav.classList.remove('is-open');
        navToggle.setAttribute('aria-expanded', 'false');
      });
    });
  }
})();
