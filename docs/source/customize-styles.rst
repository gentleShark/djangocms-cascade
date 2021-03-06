.. customized-styles:

=======================================
Customize CSS classes and inline styles
=======================================

Plugins shipped with **djangocms-cascade** offer a basic set of CSS classes as declared by the
chosen CSS framework. These offered classes normally do not fulfill the requirements for real world
sites.

While **djangocms-cascade** is easily extendible, it would be overkill to re-implement the available
plugins, just to add an extra field for a customized CSS class or an extra inline style. For that
purpose, one can add a set of potential CSS classes and potential CSS inline styles for Cascade
plugins, enabled for this feature. Moreover, this feature can be adopted individually on a per-site
base.


Configure a Cascade Plugins to accept extra fields
==================================================

Configuring a plugin to allow an HTML id tag, an extra CSS classes or some inline styles is very
easy. In the projects ``settings.py``, assure that ``'cmsplugin_cascade.extra_fields'`` is part of
your ``INSTALLED_APPS``.

Then add a list of Cascade plugins, which shall be extendible. It is a good idea to enable at least
these plugins for extendibility:

.. code-block:: python

	CMSPLUGIN_CASCADE_WITH_EXTRAFIELDS = ['BootstrapRowPlugin', 'SimpleWrapperPlugin', 'HorizontalRulePlugin']


Enable extra fields
===================

To enable this feature, in the administration backend navigate to
**Home › Cmsplugin_cascade › Custom CSS classes and styles**  and click onto the
**Add Custom CSS classes styles** button.

From the field named “Plugin Name”, for instance select **Bootstrap Simple Wrapper**. Then, from the
field named “Site”, select the current site.

|customize-styles|

.. |customize-styles| image:: /_static/customize-styles.png


Allow ID
--------

With “Allow id tag” enabled, an extra field will appear on the named plugin editor. There a user
can add any arbitrary name which will be rendered as ``id="any_name"`` for the corresponding plugin
instance.

CSS classes
-----------

In the field named “CSS class names”, the administrator may specify arbitrary CSS classes separated
by commas. One of these CSS classes then can be added to the corresponding Cascade plugin. If
more than one CSS class shall be addable concurrently, activate the checkbox named “Allow multiple”.


CSS inline styles
-----------------

The administrator may activate all kinds of CSS inline styles by clicking on the named checkbox. For
settings describing distances, additionally specify the allowed units to be used.

Now, if a user opens the corresponding plugin inside the **Structure View**, he will see an extra 
select field to choose the CSS class and some input fields to enter say, extra margins, heights or
whatever has been activated.


Use it rarely, use it wise
..........................

Adding too many styling fields to a plugin can mess up any web project. Therefore be advised to use
this feature rarely and wise. If many people have write access to plugins, set extra permissions on
this table, in order to not mess things up. For instance, it rarely makes sense to activate
``min-width``, ``width`` and ``max-width``.
