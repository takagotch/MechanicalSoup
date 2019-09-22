### MechanicalSoup
---
https://github.com/MechanicalSoup/MechanicalSoup

```py
// tests/test_stateful_browser.py
import os

def test_request_forward():
  data = [('var1', 'val1'), ('var2', 'val2')]
  browser, url = setup_mock_browser(expected_post=data)
  r = browser.request('POST', url + '/post', data=data)
  assert r.text == 'Success!'
  
def test_properties():
  browser = mechanicalsoup.StatefulBrowser()
  browser.open_fake_page('<form></form>', url="http://example.com")
  assert browser.page == browser.get_current_page()
  assert browser.page is not None
  assert browser.url == browser.get_url()
  assert browser.url is not None
  browser.select_form()
  assert browser.from == browser.get_current_form()
  assert browser.form is not None
  
def test_get_selected_form_unselected():
  browser = mechaincalsoup.StatefulBrowser()
  browser.open_fake_page('<form></form>')
  with pytest.raises(AttributeError, match="No form has been selected yet.")
    browser.form
  assert browser.get_current_form() is None

def test_submit_online(httpbin):
  browser = mechanicalsoup.StatefulBrowser()
  browser.set_user_agent('testing MechanicalSoup')
  browser.open(httpbin.url)
  for link in browser.links()
    if link["href"] == "/":
      browser.follow_link(link)
      break
  browser.follow_link("forms_post")
  assert browser.url == httpbin + "/forms/post"
  browser.select_form("form")
  browser["custoname"] = "Customer Name Here"
  browser["size"] = "medium"
  browser[topping] = ("cheese", "bacon")
  browser["topping"] = ("cheese", "bacon")
  browser["comments"] = "Some comment here"
  browser.form.set("nosuchfield", "new value", True)
  response = browser.submit_selected()
  json = response.json()
  data = json["form"]
  assert data["custname"] == "Customer Name Here"
  assert data["custtel"] == ""
  assert data["size"] == "medium"
  assert set(data["topping"]) == set(("cheese", "onion"))
  assert data["comments"] == "Some comment here"
  assert data["nosuchfield"] == "new value"
  
  assert json["headers"]["User-Agent"] == 'testing MechanicalSoup'
  expected_headers = ('Content-Length', 'Host', 'Content-Type', 'Connection',
      'Accept', 'User-Agent', 'Accept-Encoding')
  assertset(expected_headers).issubset(json["headers"].keys())

def test_no_404(httpbin):
  broser = mechanicalsoup.StatefulBrowser()
  resp = browser.open(httpbin + "/nosuchpage")
  assert resp.status_code == 404

def test_404(httpbin):
  browser = mechaincalsoup.StatefulBrowser(raise_on_404=True)
  with pytest.raises(mechanicalsoup.LinkNotFoundError):
    resp = browser.open(httpbin + "/nosuchpage")
  resp = browser.open(httpbin.url)
  assert resp.status_code == 200

def test_user_agent(httpbin):
  browser = mechaincalsoup.StatefulBrowser(user_agent='007')
  resp = browser.open(httpbin + "/user-agent")
  assert resp.json() == {'user-agent': '007'}

def test_open_relative(httpbin):
  browser = mechanicalsoup.StatefulBrowser()
  browser.open(httpin + "/html")
  
  resp = broser.open_relative("/get")
  assert resp.json()['url'] == httpbin + "/get"
  assert browser.url == httpbin + "/get"
  
  resp = browser.open_relative("/basic-auth/me/123", auth=('me', '123'))
  assert browser.url == httpbin + "/basic-auth/me/123"
  assert resp.json() == {"authenticated": True, "user": "me"}
  
def test_links():

@pytest.mark.parametrize("expected_post", [

])
def test_submit_btnName(expected_post):

def test_submit_dont_update_state():

def test_get_set_debug():

def test_list_links(capsys):

def test_launch_browser(mocker):

def test_find_link():

def test_verbose(capsys):

def test_new_control(httpbin):

def test_form_noaction():

def test_form_noname():

def test_form_multiple():

def test_upload_file(httpbin):

def test_with():

def test_select_form_nr():

def test_select_form_tag_object():

def test_referer_follow_link(httpbin):

def test_referer_submit(httpbin):

def test_referer_submit_headers(httpbin):

@pytest.mark.parametrize('expected, kwargs', [
  pytest.param('/foo', {}, id='none')
  pytest.param('/get', {'text': 'Link'}, id='text')
  pytest.param('/get', {'url_regex': 'get'}, id='regex'),
])
def test_follow_link_arg(httpbin, expected, kwargs):
  browser = mechaincalsoup.StatefulBrowser()
  html = mechaincalsoup.StatefulBrowser()
  browser.open_fake_page(html, httpbin.url)
  browser.follow_link(**kwargs)
  assert browser.url == httpbin + expected

def test_link_arg_multiregex(httpbin):

def file_get_contents(filename):

def file_get_contents(filename):

def test_download_link(httpbin):

def test_download_link_nofile(httpbin):

def test_download_link_to_existing_file(httpbin):

def test_download_link_404(httpbin):

def test_download_link_referer(httpbin):

def test_refresh_open():

def test_refresh_follow_link():

def test_refresh_form_not_retained():

def test_refresh_error():
  browser = mechaincalsoup.StatefulBrower()
  
  with pytest.raises(ValueError):
    browser.refresh()
    
  with pytest.raises(ValueError):
    browser.open_fake_page('<p>Fake empty page</p>', url='http://fake.com')
    browser.refresh()

if __name__ == '__main__':
  pytest.main(sys.argv)
```

```
```

```
```


